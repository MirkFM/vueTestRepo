<template lang="pug">
  include ../tools/mixins.pug

  +b.s-payment-form
    .wrapper
      .wrap-in
        +e.title= data("form.title")
        +e.order= data("form.order.title")
        +e.sum
          +e.A.sum-total= data("form.order.sum")
          +e.sum-border
        +e.FORM.form
          +e.field.cardnumber
            +e.INPUT.input(type="tel" value=data("form.field.cardnumber.val") placeholder=data("form.field.cardnumber.placeholder"))
            +e.hint
              +e.hint-text
                +e.hint-help=data("form.field.cardnumber.hint.help")
                +e.hint-error=data("form.field.cardnumber.hint.error")

          +e.field-group
            +e.field.expdate
              +e.INPUT.input(type="tel" value=data("form.field.expdate.val") placeholder=data("form.field.expdate.placeholder"))
              +e.hint
                +e.hint-text
                  +e.hint-help=data("form.field.expdate.hint.help")
                  +e.hint-error=data("form.field.expdate.hint.error")
            +e.field.cvc
              +e.INPUT.input(type="tel" value=data("form.field.cvc.val") placeholder=data("form.field.cvc.placeholder"))
              +e.hint
                +e.hint-text
                  +e.hint-help=data("form.field.cvc.hint.help")
                  +e.hint-error=data("form.field.cvc.hint.error")

          +e.field.cardholder
            +e.INPUT.input(type="text" value=data("form.field.cardholder.val") placeholder=data("form.field.cardholder.placeholder"))
            +e.hint
              +e.hint-text
                +e.hint-help=data("form.field.cardholder.hint.help")
                +e.hint-error=data("form.field.cardholder.hint.error")

          +e.field.email
            +e.INPUT.input(type="mail" value=data("form.field.email.val") placeholder=data("form.field.email.placeholder"))
            +e.hint
              +e.hint-text
                +e.hint-help=data("form.field.email.hint.help")
                +e.hint-error=data("form.field.email.hint.error")

          +e.field.phone
            +e.INPUT.input(type="phone" value=data("form.field.phone.val") placeholder=data("form.field.phone.placeholder"))
            +e.hint
              +e.hint-text
                +e.hint-help=data("form.field.phone.hint.help")
                +e.hint-error=data("form.field.phone.hint.error")

          +e.field.city
            +e.INPUT.input(type="text" value=data("form.field.city.val") placeholder=data("form.field.city.placeholder"))
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
export default {
  name: 'PaymentForm',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App',
    };
  },
};
</script>
