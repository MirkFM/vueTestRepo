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
import EmailMask from 'text-mask-addons/dist/emailMask';

export default {
  name: 'EmailMaskInput',

  components: {
    MaskedInput,
  },

  data() {
    return {
      value: '',
      mask: EmailMask,
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
