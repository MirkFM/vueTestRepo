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
  name: 'CityMaskInput',

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
      return { B: { pattern: /[-a-zA-Zа-яА-Я ]/ } };
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
