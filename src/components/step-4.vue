<template>
  <div class="step-4">
    <h5>Finishing Up</h5>
    <p>Double-check everything looks OK before confirming.</p>
    <div class="step-4-cont">
      <div class="plan-choose">
        <h5>
          <span class="total-text-span-2">arcades</span>
          <span class="total-text-span">(monthly)</span>
        </h5>
        <h5 class="price-plan-total">$9/mo</h5>
      </div>
      <hr />

      <p class="change">change</p>
      <div class="addons-list-total"></div>
      <!-- <div class="add-ons-choose">
                      <p>online service</p>
                      <p>$1/mo</p>
                    </div>
                    <div class="add-ons-choose">
                      <p>Larger Storage</p>
                      <p>$2/mo</p>
                    </div>
                  </div> -->
    </div>
    <div class="total">
      <div class="total-text">
        <p>Total(monthly)</p>
      </div>
      <div class="price-total">$12/mo</div>
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
});
</script>
