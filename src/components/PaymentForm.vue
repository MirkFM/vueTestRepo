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
          <div class="s-form__field cardnumber">
            <card-number
              placeholder="Номер карты"
              name="cardnumber"
              class="s-form__input"
            />

            <div class="s-form__hint">
              <div class="s-form__hint-text">
                <div class="s-form__hint-help">Текст подсказки для поля</div>
                <div class="s-form__hint-error">Данное поле обязательно для заполнения</div>
              </div>
            </div>
          </div>
          <div class="s-form__field-group">
            <div class="s-form__field expdate">
              <exp-date
                class="s-form__input"
                placeholder="ММ / ГГ"
              />
              <div class="s-form__hint">
                <div class="s-form__hint-text">
                  <div class="s-form__hint-help">Текст подсказки для поля</div>
                  <div class="s-form__hint-error">Данное поле обязательно для заполнения</div>
                </div>
              </div>
            </div>
            <div class="s-form__field cvc">
              <cvc
                placeholder="Cvc"
                name="cvc"
                class="s-form__input"
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
          <div class="s-form__field email">
            <input class="s-form__input" type="mail" value="" placeholder="E-mail" />
            <div class="s-form__hint">
              <div class="s-form__hint-text">
                <div class="s-form__hint-help">Текст подсказки для поля</div>
                <div class="s-form__hint-error">Данное поле обязательно для заполнения</div>
              </div>
            </div>
          </div>
          <div class="s-form__field phone">
            <phone-mask-input></phone-mask-input>

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
import PhoneMaskInput from './PhoneMaskInput';
import CardNumber from './CardNumberMaskInput';
import Cvc from './CvcMaskInput';
import ExpDate from './ExpDateMaskInput';


export default {
  name: 'PaymentForm',

  components: {
    PhoneMaskInput,
    CardNumber,
    Cvc,
    ExpDate,
  },

  data() {
    return {
      form: {
        cardnumber: '',
        expdate: '',
        cvc: '',
        cardholder: '',
        email: '',
        phone: '',
        city: '',
      },
    };
  },
};
</script>
