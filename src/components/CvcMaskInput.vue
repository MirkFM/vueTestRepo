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
  name: 'CvcMaskInput',

  components: {
    MaskedInput,
  },

  data() {
    return {
      value: '',
      paymentSystem: '',
    };
  },

  computed: {
    mask() {
      if (this.paymentSystem === 'maestro') {
        return [
          /\d/, /\d/, /\d/, /\d/,
        ];
      }

      return [
        /\d/, /\d/, /\d/,
      ];
    },
  },

  methods: {
    handleFocus() {
      this.$emit('focus');
    },
    handleBlur() {
      this.$emit('blur');

      console.log(this.$data.value);

      if (this.$data.value === '') {
        this.$emit('error');
      } else {
        this.$emit('valid');
      }
    },
  },
};
</script>
