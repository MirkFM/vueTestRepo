<template>
  <masked-input
    type="text"
    name="phone"
    class="s-form__input"
    v-model="phone"
    :mask="[
      '+', '7', ' ',
      '(', /[1-9]/, /\d/, /\d/, ')', ' ',
      /\d/, /\d/, /\d/, '-', /\d/, /\d/, /\d/, /\d/
    ]"
    :guide="true"
    placeholder="Телефон"
    placeholderChar="\u2000">
  </masked-input>
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
      phone: '',
    };
  },
};
</script>

