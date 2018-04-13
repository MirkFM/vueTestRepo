<template>
  <masked-input
    name="expdate"
    v-model="phone"
    :mask="[/\d/, /\d/, ' ', '\/', ' ', /\d/, /\d/]"
    :guide="true"
    :pipe=autoCorrectedDatePipe
    placeholderChar="X">
  </masked-input>
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
      phone: '',
      autoCorrectedDatePipe: createAutoCorrectedDatePipe('dd / yy'),
    };
  },
};
</script>
