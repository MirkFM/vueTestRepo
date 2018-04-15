<template>
  <the-mask
    :mask=mask
    v-model=value
    @focus.native="handleFocus"
    @blur.native="handleBlur"
  />
</template>

<script>
import { TheMask } from 'vue-the-mask';

export default {
  name: 'CardNumberMaskInput',

  components: {
    TheMask,
  },

  data() {
    return {
      value: '',
      paymentSystem: 'visa',
    };
  },

  computed: {
    mask() {
      if (this.paymentSystem === 'visa') {
        return ['#### #### #### ####', '#### #### #### #### #', '#### #### #### #### ##', '#### #### #### #### ###'];
      }

      return ['#### #### #### ####'];
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
