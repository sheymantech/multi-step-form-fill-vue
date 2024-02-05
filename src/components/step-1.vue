<template>
  <div class="step-1">
    <h5>personal info</h5>
    <p>Please provide your name, email address, and phone number.</p>

    <form @submit.prevent="handleSubmitForm">
      <span>Name</span>
      <input type="text" placeholder="e.g.stephen king" v-model="name" />
      <div class="label-wrapper">
        <label>Email</label>
        <label class="danger hidden">
          This field is required in mail format</label
        >
      </div>
      <input
        type="email"
        placeholder="e.g.olaniyansheyi1704@gmail.com"
        id="input-email"
        v-model="email"
      />
      <div class="label-wrapper">
        <label class="">Phone Number</label>
        <label class="danger hidden"> This field is required </label>
      </div>
      <input
        type="text"
        placeholder="e.g.+1 234 567 890"
        id="input-num"
        v-model="phoneNumber"
      />
      <button class="next-step-1 btn-step-1">Next step</button>
    </form>
  </div>
</template>

<script setup>
import { useToast } from "vue-toastification";

import { defineProps, ref } from "vue";
const toast = useToast();
const email = ref("");
const phoneNumber = ref("");
const name = ref("");
const props = defineProps({
  nextStep: {
    type: Function,
    required: true,
  },
});
const handleSubmitForm = function () {
  if (!email.value || !name.value || !phoneNumber.value) {
    toast.error("All the forms are strictly required!");
  } else {
    props.nextStep();
    toast.success("form submited successfully!");
  }
};
</script>
