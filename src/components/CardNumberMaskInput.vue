<template>
  <the-mask
    :mask=mask
    v-model=value
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
};
</script>
