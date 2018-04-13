<template>
  <masked-input
    name="expdate"
    v-model="value"
    :mask=mask
    :guide="true"
    placeholderChar="X">
  </masked-input>
</template>

<script>
import MaskedInput from 'vue-text-mask';
import EmailMask from 'text-mask-addons/dist/emailMask';

export default {
  name: 'ExpDateMaskInput',

  components: {
    MaskedInput,
  },

  data() {
    return {
      value: '',
      mask: EmailMask,
    };
  },
};
</script>
