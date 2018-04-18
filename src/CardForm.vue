<template lang="pug">
  extends ./tools/_layout.pug

  block content
    +e.FORM.form
      +formField('cardnumber')
        +e.hint
          +e.hint-text
            +e.hint-help=data("form.field.cardnumber.hint.help")
            +e.hint-error=data("form.field.cardnumber.hint.error")

      +e.field-group
        +formField('expdate')
          +e.hint
            +e.hint-text
              +e.hint-help=data("form.field.expdate.hint.help")
              +e.hint-error=data("form.field.expdate.hint.error")
        +formField('cvc')
          +e.hint
            +e.hint-text
              +e.hint-help=data("form.field.cvc.hint.help")
              +e.hint-error=data("form.field.cvc.hint.error")

      +formField('cardholder')
        +e.hint
          +e.hint-text
            +e.hint-help=data("form.field.cardholder.hint.help")
            +e.hint-error=data("form.field.cardholder.hint.error")

      +formField('email')
        +e.hint
          +e.hint-text
            +e.hint-help=data("form.field.email.hint.help")
            +e.hint-error=data("form.field.email.hint.error")

      +formField('phone')
        +e.hint
          +e.hint-text
            +e.hint-help=data("form.field.phone.hint.help")
            +e.hint-error=data("form.field.phone.hint.error")

      +formField('city')
        +e.hint
          +e.hint-text
            +e.hint-help=data("form.field.city.hint.help")
            +e.hint-error=data("form.field.city.hint.error")

      +e.check-group
        +e.INPUT.check(type='checkbox' name="contact" value="phone" id="check-1")
        +e.LABEL.label(for="check-1" checked)=data("form.send.receipt.label")

      +e.field
        +e.INPUT.button.button(type='submit' value=data("form.btn.submit.val"))
</template>

<script>
import Cardnumber from './components/CardNumberMaskInput';
import Expdate from './components/ExpDateMaskInput';
import Cvc from './components/CvcMaskInput';
import Cardholder from './components/CardHolderMaskInput';
import Email from './components/EmailMaskInput';
import Phone from './components/PhoneMaskInput';
import City from './components/CityMaskInput';

export default {
  name: 'CardForm',

  components: {
    Cardnumber,
    Expdate,
    Cvc,
    Cardholder,
    Email,
    Phone,
    City,
  },

  data() {
    return {
      cardnumber: {
        value: '',
        valid: null,
        focused: true,
      },
      expdate: {
        value: '',
        valid: null,
        focused: false,
      },
      cvc: {
        value: '',
        valid: null,
        focused: false,
      },
      cardholder: {
        value: '',
        valid: null,
        focused: false,
      },
      email: {
        value: '',
        valid: null,
        focused: false,
      },
      phone: {
        value: '',
        valid: null,
        focused: false,
      },
      city: {
        value: '',
        valid: null,
        focused: false,
      },
    };
  },
};
</script>
