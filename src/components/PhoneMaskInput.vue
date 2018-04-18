<template>
  <masked-input
    v-model="value"
    :mask="mask"
    :guide="true"
    placeholderChar="X"
    @focus.native="handleFocus"
    @blur.native="handleBlur"
  />
</template>

<script>
import MaskedInput from 'vue-text-mask';

export default {
  name: 'PhoneMaskInput',

  components: {
    MaskedInput,
  },

  data() {
    return {
      value: '',
    };
  },

  methods: {
    handleFocus() {
      this.$emit('focus');
    },
    handleBlur() {
      this.$emit('blur');

      if (this.$data.value === '') {
        this.$emit('error');
      } else {
        this.$emit('valid');
      }
    },
    mask(rawValue) {
      const startSymbolPosition = rawValue.search(/[+1-9]/);
      const startSymbol = rawValue[startSymbolPosition];

      if (startSymbol === '8') {
        return ['8', ' ',
          '(', /[1-9]/, /\d/, /\d/, ')', ' ',
          /\d/, /\d/, /\d/, '-', /\d/, /\d/, '-', /\d/, /\d/,
        ];
      }

      return ['+', /[1-7]/, ' ',
        '(', /[1-9]/, /\d/, /\d/, ')', ' ',
        /\d/, /\d/, /\d/, '-', /\d/, /\d/, '-', /\d/, /\d/,
      ];
    },
  },
};
</script>

