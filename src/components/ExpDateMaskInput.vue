<template>
  <masked-input
    name="expdate"
    v-model="value"
    :mask="[/\d/, /\d/, ' ', '\/', ' ', /\d/, /\d/]"
    :guide="true"
    :pipe=autoCorrectedDatePipe
    placeholderChar="X"
    @focus.native="handleFocus"
    @blur.native="handleBlur"
  />
</template>

<script>
import MaskedInput from 'vue-text-mask';
import createAutoCorrectedDatePipe from 'text-mask-addons/dist/createAutoCorrectedDatePipe';

export default {
  name: 'ExpDateMaskInput',

  components: {
    MaskedInput,
  },

  data() {
    return {
      value: '',
      autoCorrectedDatePipe: createAutoCorrectedDatePipe('dd / yy'),
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
  },
};
</script>
