<template>
  <the-mask
    :mask=mask
    v-model=value
  />
</template>

<script>
import { TheMask } from 'vue-the-mask';

export default {
  name: 'CvcMaskInput',

  components: {
    TheMask,
  },

  data() {
    return {
      value: '',
      paymentSystem: 'maestro',
    };
  },
  computed: {
    mask() {
      if (this.paymentSystem === 'maestro') {
        return ['###', '####'];
      }

      return ['###'];
    },
  },
};
</script>
