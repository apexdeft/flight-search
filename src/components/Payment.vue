<template>
  <div class="row bg">
    <div class="col-12">
      <h3>Payment</h3>
      {{ $route.params.bookingKey }}
      <div class="text-left">
        <b-card no-body>
          <b-tabs card>
            <b-tab title="Credit Card" active>
              <b-card-text>
                <h3>Credit Card</h3>
                <CardForm
                  :form-data="formData"
                  @input-card-number="updateCardNumber"
                  @input-card-name="updateCardName"
                  @input-card-month="updateCardMonth"
                  @input-card-year="updateCardYear"
                  @input-card-cvv="updateCardCvv"
                />
                <p>Activate your KTB, Bangkok Bank, SCB, KBank, Bank of Ayudhya, Thanachart Bank Debit Card: See instructions here.</p>
              </b-card-text>
            </b-tab>
            <b-tab title="K PLUS">
              <b-card-text>
                <h3>K PLUS</h3>
                <p>Before continue, please turn on K Plus Application notification.</p>
                <p>
                  Please enter Mobile Number that linked to your K Plus Account K plus
                  <img
                    src="https://p-a.popcdn.net/assets/payments/k-plus-ce68a718bad6d2e989dc1fce165246a8ceda61fe571530c8cd2825d947745e9e.png"
                    alt
                  />
                </p>
                <p>
                  * Mobile Number
                  <input type="text" name="tel" />
                </p>
              </b-card-text>
            </b-tab>
            <b-tab title="Bill Payment">
              <b-card-text>
                <h3>How To Pay</h3>
                <p>Please print the bill payment instrunctions and pay in cash at any bill payment cashiers/banks listed in the bill.</p>

                <img
                  src="https://p-a.popcdn.net/assets/pdf/123-counter-logos-23e1194d7036f9ec8551f953c02ad7788a954fbbac9d490977fe2de35c2a21ff.png"
                  alt
                />
                <img
                  src="https://p-a.popcdn.net/assets/pdf/123-cenpay-logos-30b40239084254773c738384743beb577ea4d19a3c2fe5f9c3dde6402b780333.png"
                  alt
                />
                <img
                  src="https://p-a.popcdn.net/assets/pdf/123-bank-logos-57d1047d06996ec605a3f8e176309365d7a3ffbcbbc6c2b3f45230f27ca69f59.png"
                  alt
                />

                <h3>Order Cancellation Policy</h3>
                <p>Please pay within expiry date and time. Otherwise this order will be cancelled automatically by the system.</p>

                <p>
                  Remark:
                  <br />1. Bill payment can pay up to THB 30,000 only.
                  <br />2. If the payment made after order was expired or paid amount are not correct, Event Pop Co., Ltd. reserve to not refund under any circumstance.
                  <br />
                </p>
              </b-card-text>
            </b-tab>
            <b-tab title="Alipay">
              <b-card-text>
                <h3>Alipay</h3>
                <img
                  src="https://p-a.popcdn.net/assets/payments/alipay-icon-4d476c6b1716754a7682d561d5758bf66b4ae54c419b0908662ece3c3873f6c8.png"
                  alt
                />
                <p>After clicking " Confirm" your order is not yet complete, you will be redirected to another page to proceed your payment with Alipay.</p>
                <p>* Please complete the transaction within the remaining time.</p>
              </b-card-text>
            </b-tab>
          </b-tabs>
        </b-card>
      </div>
    </div>
  </div>
</template>

<script>
import CardForm from "@/components/CardForm";

export default {
  name: "Payment",
  components: {
    CardForm
  },
  data() {
    return {
      formData: {
        cardName: "",
        cardNumber: "",
        cardMonth: "",
        cardYear: "",
        cardCvv: ""
      }
    };
  },
  props: {
    msg: String
  },
  methods: {
    updateCardNumber(val) {
      console.log(val);
    },
    updateCardName(val) {
      console.log(val);
    },
    updateCardMonth(val) {
      console.log(val);
    },
    updateCardYear(val) {
      console.log(val);
    },
    updateCardCvv(val) {
      console.log(val);
    },
    credit_card_form: function(bookingKey) {
      this.$router.push({
        name: "Payment",
        params: { bookingKey: bookingKey }
      });
    }
  }
};
</script>

<style lang="scss">
@import "../assets/style.scss";
</style>
