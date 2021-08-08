<template>
  <div class="home">
    <Navbar />
    <div class="container">
      <Hero />

      <div class="row mt-4">
        <div class="col">
          <h2>Best <strong>Food</strong></h2>
        </div>
        <div class="col">
          <router-link to="/food" class="btn btn-success float-right">
            <b-icon-eye></b-icon-eye> Lihat semua</router-link
          >
        </div>
      </div>
      <div class="row mb-3">
        <div style="display: flex; flex-direction: row">
          <v-otp-input
            ref="otpInput"
            input-classes="otp-input"
            separator=" "
            :num-inputs="12"
            :should-auto-focus="true"
            :is-input-num="false"
            @on-change="handleOnChange"
            @on-complete="handleOnComplete"
          />

          <!-- <button @click="handleClearInput()">Clear Input</button> -->
        </div>
      </div>
      <div class="row mb-3">
        <div
          class="col-md-4 mt-4"
          v-for="product in products"
          :key="product.id"
        >
          <CardProduct :product="product" />Î
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Hero from "@/components/Hero.vue";
import CardProduct from "@/components/CardProduct.vue";
import axios from "axios";
import OtpInput from "@/components/OtpInput.vue";

export default {
  name: "Home",
  components: {
    Navbar,
    Hero,
    CardProduct,
    "v-otp-input": OtpInput,
  },
  data() {
    return {
      products: [],
    };
  },
  methods: {
    setProduct(data) {
      this.products = data;
      console.log(this.products);
    },
    handleOnComplete(value) {
      console.log("OTP completed: ", value);
    },
    handleOnChange(value) {
      console.log("OTP changed: ", value);
    },
    handleClearInput() {
      this.$refs.otpInput.clearInput();
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/best-products")
      .then((response) => {
        this.setProduct(response.data);
      })
      .catch(function (error) {
        console.log(error);
      })
      .then(function () {});
  },
};
</script>

<style>
.otp-input {
  width: 40px;
  height: 40px;
  padding: 5px;
  margin: 0 10px;
  font-size: 20px;
  border-radius: 4px;
  border: 1px solid rgba(0, 0, 0, 0.3);
  text-align: center;
  /* &.error {
      border: 1px solid red !important;
    } */
}
.otp-input::-webkit-inner-spin-button,
.otp-input::-webkit-outer-spin-button {
  -webkit-appearance: none;
  margin: 0;
}
</style>