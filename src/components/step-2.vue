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
      >
        <img :src="plan.img" alt="" />
        <div class="plan-cont-wrapper">
          <h4>{{ plan.name }}</h4>
          <p class="price-year1">
            $
            {{
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
});

let switchBtn = ref(false);

let selectedPlan = ref();
const plans = ref([
  {
    name: "Arcades",
    priceMonthly: 9,
    priceYearly: 90,
    img: "../assets/img/icon-arcade.svg",
    id: 1,
  },
  {
    name: "Advance",
    priceMonthly: 12,
    priceYearly: 120,
    img: "../assets/img/icon-advanced.svg",
    id: 2,
  },
  {
    name: "Pro",
    priceMonthly: 15,
    priceYearly: 150,
    img: "../assets/img/icon-pro.svg",
    id: 3,
  },
]);

const switchToggle = () => {
  switchBtn.value = !switchBtn.value;
};
const handleSelectedPlan = function (plan) {
  switchBtn.value
    ? (selectedPlan.value = plan.priceYearly)
    : (selectedPlan.value = plan.priceMonthly);
  console.log(selectedPlan);
};

const emit = defineEmits(["SwitchToggleCheck", "selectedPlan"]);
emit("SwitchToggleCheck", switchBtn);
emit("selectedPlan", selectedPlan);
</script>
