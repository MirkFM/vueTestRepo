<template lang="html">
  <div class="s-form">
    <div class="wrapper">
      <div class="wrap-in">
        <div class="s-form__title">Avito.ru</div>
        <div class="s-form__order">Заказ №123456</div>
        <div class="s-form__sum">
          <a class="s-form__sum-total">1000₽</a>
          <div class="s-form__sum-border"></div>
        </div>
        <form class="s-form__form">
          <div class="s-form__field cardnumber" :class="[{
            focus: cardnumber.focused === true,
            valid: cardnumber.valid === true,
            error: cardnumber.valid === false,
          }]">
            <card-number
              placeholder="Номер карты"
              name="cardnumber"
              class="s-form__input"
              @focus="cardnumber.focused = true"
              @blur="cardnumber.focused = false"
              @valid="cardnumber.valid = true"
              @error="cardnumber.valid = false"
            />

            <div class="s-form__hint">
              <div class="s-form__hint-text">
                <div class="s-form__hint-help">Текст подсказки для поля</div>
                <div class="s-form__hint-error">Данное поле обязательно для заполнения</div>
              </div>
            </div>
          </div>
          <div class="s-form__field-group">
            <div class="s-form__field expdate" :class="[{
              focus: expdate.focused === true,
              valid: expdate.valid === true,
              error: expdate.valid === false,
            }]">
              <exp-date
                class="s-form__input"
                name="expdate"
                placeholder="ММ / ГГ"
                @focus="expdate.focused = true"
                @blur="expdate.focused = false"
                @valid="expdate.valid = true"
                @error="expdate.valid = false"
              />
              <div class="s-form__hint">
                <div class="s-form__hint-text">
                  <div class="s-form__hint-help">Текст подсказки для поля</div>
                  <div class="s-form__hint-error">Данное поле обязательно для заполнения</div>
                </div>
              </div>
            </div>
            <div class="s-form__field cvc" :class="[{
              focus: cvc.focused === true,
              valid: cvc.valid === true,
              error: cvc.valid === false,
            }]">
              <cvc
                placeholder="Cvc"
                name="cvc"
                class="s-form__input"
                @focus="cvc.focused = true"
                @blur="cvc.focused = false"
                @valid="cvc.valid = true"
                @error="cvc.valid = false"
              />

              <div class="s-form__hint">
                <div class="s-form__hint-text">
                  <div class="s-form__hint-help">Текст подсказки для поля</div>
                  <div class="s-form__hint-error">Данное поле обязательно для заполнения</div>
                </div>
              </div>
            </div>
          </div>
          <div class="s-form__field cardholder">

            <input class="s-form__input" type="text" value="" placeholder="Держатель карты" />
            <div class="s-form__hint">
              <div class="s-form__hint-text">
                <div class="s-form__hint-help">Текст подсказки для поля</div>
                <div class="s-form__hint-error">Данное поле обязательно для заполнения</div>
              </div>
            </div>
          </div>
          <div class="s-form__field email" :class="[{
            focus: email.focused === true,
            valid: email.valid === true,
            error: email.valid === false,
          }]">
            <email
              placeholder="E-mail"
              name="email"
              class="s-form__input"
              @focus="email.focused = true"
              @blur="email.focused = false"
              @valid="email.valid = true"
              @error="email.valid = false"
            />
            <div class="s-form__hint">
              <div class="s-form__hint-text">
                <div class="s-form__hint-help">Текст подсказки для поля</div>
                <div class="s-form__hint-error">Данное поле обязательно для заполнения</div>
              </div>
            </div>
          </div>
          <div class="s-form__field phone" :class="[{
            focus: phone.focused === true,
            valid: phone.valid === true,
            error: phone.valid === false,
          }]">
            <phone
              placeholder="Телефон"
              name="phone"
              class="s-form__input"
              @focus="phone.focused = true"
              @blur="phone.focused = false"
              @valid="phone.valid = true"
              @error="phone.valid = false"
            />

            <div class="s-form__hint">
              <div class="s-form__hint-text">
                <div class="s-form__hint-help">Текст подсказки для поля</div>
                <div class="s-form__hint-error">Данное поле обязательно для заполнения</div>
              </div>
            </div>
          </div>
          <div class="s-form__field city">
            <input class="s-form__input" type="text" value="" placeholder="Город" />
            <div class="s-form__hint">
              <div class="s-form__hint-text">
                <div class="s-form__hint-help">Текст подсказки для поля</div>
                <div class="s-form__hint-error">Данное поле обязательно для заполнения</div>
              </div>
            </div>
          </div>
          <div class="s-form__check-group">
            <input class="s-form__check" type="checkbox" name="contact" value="phone" id="check-1" />
            <label class="s-form__label" for="check-1" checked="checked">Отправить подтверждение на email</label>
          </div>
          <div class="s-form__field">
            <input class="s-form__button button" type="submit" value="Оплатить 1000₽" />
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import Phone from './PhoneMaskInput';
import CardNumber from './CardNumberMaskInput';
import Cvc from './CvcMaskInput';
import ExpDate from './ExpDateMaskInput';
import Email from './EmailMaskInput';


export default {
  name: 'PaymentForm',

  components: {
    Phone,
    CardNumber,
    Cvc,
    ExpDate,
    Email,
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

  mounted() {
    this.$on('focus', (flag) => {
      console.log('focus', flag);
    });
  },
};
</script>
