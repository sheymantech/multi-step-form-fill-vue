<template>
  <div class="step-4">
    <h5>Finishing Up</h5>
    <p>Double-check everything looks OK before confirming.</p>
    <div class="step-4-cont">
      <div class="plan-choose">
        <h5>
          <span class="total-text-span-2">{{ selectedPlanName.name }}</span>
          <span class="total-text-span">{{
            `${switchBtn ? "(Yearly)" : "(Monthly)"}`
          }}</span>
        </h5>
        <h5 class="price-plan-total">
          {{ `$${selectedPlanName.price}/${switchBtn ? "Yr" : "Mo"}` }}
        </h5>
      </div>
      <hr />

      <p class="change" @click="change">change</p>
      <div class="addons-list-total"></div>
      <div class="add-ons-choose" v-for="selectedAddon in selectedAddons">
        <p>{{ selectedAddon.name }}</p>
        <p>{{ `$${selectedAddon.price}/${switchBtn ? "Yr" : "Mo"}` }}</p>
      </div>
    </div>
    <div class="total">
      <div class="total-text">
        <p>Total {{ `(${switchBtn ? "Yearly" : "Monthly"})` }}</p>
      </div>
      <div class="price-total">
        {{ `$${allTotal}/${switchBtn ? "Yr" : "Mo"}` }}
      </div>
    </div>
    <button class="next-step-4 btn-step-4 mt-5" @click="nextStep">
      Confirm
    </button>
    <button class="go-back-step-4 btn-back-4 mt-5" @click="prevStep">
      Go Back
    </button>
  </div>
</template>
<script setup>
import { defineProps } from "vue";

const props = defineProps({
  nextStep: {
    type: Number,
    required: true,
  },
  prevStep: {
    type: Number,
    required: true,
  },
  change: {
    type: Number,
    required: true,
  },
  selectedAddons: {
    type: Array,
    required: true,
  },
  switchBtn: {
    type: Boolean,
    required: true,
  },
  allTotal: {
    type: Number,
    required: true,
  },
  selectedPlanName: {
    type: Object,
    required: true,
  },
});
</script>
