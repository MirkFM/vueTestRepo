<template>
  <masked-input
    type="text"
    name="phone"
    class="s-form__input"
    v-model=value
    :mask="[
      '+', '7', ' ',
      '(', /[1-9]/, /\d/, /\d/, ')', ' ',
      /\d/, /\d/, /\d/, '-', /\d/, /\d/, /\d/, /\d/
    ]"
    :guide="true"
    placeholder="Телефон"
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
  },
};
</script>

