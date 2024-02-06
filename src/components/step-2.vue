<template>
  <div class="step-2">
    <h5>Select your plan</h5>
    <p>you have the option of monthly or yearly billing.</p>
    <div class="row plans-cont">
      <div
        data-price-yearly="90"
        data-price-monthly="9"
        class="col-lg-3 col-4 plans ms-3"
        v-for="plan in plans"
        :key="plan.id"
        @click="handleSelectedPlan(plan)"
        :class="{ activePlan: plan.active }"
      >
        <img src="../assets/img/icon-pro.svg" alt="" />
        <div class="plan-cont-wrapper">
          <h4>{{ plan.name }}</h4>
          <p class="price-year1">
            $
            {{css: ['assets/normalize.css'],
              switchBtn ? `${plan.priceYearly}/Yr` : `${plan.priceMonthly}/Mo`
            }}
          </p>
          <h6 class="hidden year-plan" :class="{ show: switchBtn }">
            2 months free
          </h6>
        </div>
      </div>
    </div>
    <div class="plan-duration">
      <h6>monthly</h6>
      <div class="switch-cont">
        <div
          class="switch-toggle"
          @click="switchToggle"
          :class="{ msAuto: switchBtn }"
        ></div>
      </div>
      <h6>yearly</h6>
    </div>
    <button class="next-step-2 btn-step-2 mt-5" @click.prevent="nextStep">
      Next step
    </button>
    <button class="go-back-step-2 btn-back-2 mt-5" @click="prevStep">
      Go Back
    </button>
  </div>
</template>

<script setup>
import { defineProps, ref } from "vue";

const props = defineProps({
  nextStep: {
    type: Number,
    required: true,
  },
  prevStep: {
    type: Number,
    required: true,
  },
  plans: {
    type: Array,
    required: true,
  },
  switchToggle: {
    type: Number,
    required: true,
  },
  handleSelectedPlan: {
    type: Number,
    required: true,
  },
  switchBtn: Boolean,
});
</script>
