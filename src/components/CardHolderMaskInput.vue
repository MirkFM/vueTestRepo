<template>
  <the-mask
    v-model=value
    :mask=mask
    :tokens=tokens
    @focus.native="handleFocus"
    @blur.native="handleBlur"
  />
</template>

<script>
import { TheMask } from 'vue-the-mask';

export default {
  name: 'CardHolderMaskInput',

  components: {
    TheMask,
  },

  data() {
    return {
      value: '',
    };
  },

  computed: {
    mask() {
      const N = Number(this.$data.value.length) + 2;

      return Array(N).join('B');
    },

    tokens() {
      return { B: { pattern: /[a-zA-Z ]/, transform: v => v.toLocaleUpperCase() } };
    },
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
