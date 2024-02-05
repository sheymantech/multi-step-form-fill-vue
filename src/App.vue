<template>
  <img
    src="./assets/img/bg-sidebar-mobile.svg"
    class="hidden img-mobile"
    alt=""
  />
  <div class="container">
    <div class="row">
      <div class="col-lg-12 mx-auto col-md-10 body-cont">
        <div class="row">
          <div class="col-lg-4 me-lg-5">
            <img
              src="./assets/img/bg-sidebar-desktop.svg"
              class="img-desktop"
              alt=""
            />
          </div>
          <div class="col-lg-7 col-md-8 cont-wrapper mt-5">
            <step1 v-if="currentStep === 1" :nextStep="nextStep" />
            <step2
              v-if="currentStep === 2"
              :nextStep="nextStep"
              :prevStep="prevStep"
              :plans="plans"
              :switchToggle="switchToggle"
              :handleSelectedPlan="handleSelectedPlan"
              :switchBtn="switchBtn"
            />
            <step3
              v-if="currentStep === 3"
              :nextStep="nextStep"
              :prevStep="prevStep"
              :addons="addons"
              :switchChecker="switchBtn"
              :handleSelectedAddons="handleSelectedAddons"
            />
            <step4
              v-if="currentStep === 4"
              :nextStep="nextStep"
              :prevStep="prevStep"
              :change="change"
              :selectedAddons="selectedAddons"
              :switchBtn="switchBtn"
              :allTotal="allTotal"
              :selectedPlanName="selectedPlanName"
            />
            <step5 v-if="currentStep === 5" />
          </div>
        </div>

        <div class="progress-wrapper text-white">
          <div class="progress-bar">
            <div
              class="progress-bar-box box-1"
              :class="{ active: currentStep === 1 }"
            >
              1
            </div>
            <div class="progress-bar-cont">
              <p>STEP 1</p>
              <h6>YOUR INFO</h6>
            </div>
          </div>
          <div class="progress-bar">
            <div
              class="progress-bar-box box-2"
              :class="{ active: currentStep === 2 }"
            >
              2
            </div>
            <div class="progress-bar-cont">
              <p>STEP 2</p>
              <h6>HOST PLAN</h6>
            </div>
          </div>
          <div class="progress-bar">
            <div
              class="progress-bar-box box-3"
              :class="{ active: currentStep === 3 }"
            >
              3
            </div>
            <div class="progress-bar-cont">
              <p>STEP 3</p>
              <h6>ADD-ONS</h6>
            </div>
          </div>
          <div class="progress-bar">
            <div
              class="progress-bar-box box-4"
              :class="{ active: currentStep === 4 }"
            >
              4
            </div>
            <div class="progress-bar-cont">
              <p>STEP 4</p>
              <h6>SUMMARY</h6>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- <div class="p-5 copy-write">
    Challenge by
    <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
      >Frontend Mentor</a
    >. Coded by <a href="https://twitter.com/olaniyanoe1704">olaniyan sheyi</a>.
  </div> -->
</template>

<script setup>
import step1 from "./components/step-1.vue";
import step2 from "./components/step-2.vue";
import step3 from "./components/step-3.vue";
import step4 from "./components/step-4.vue";
import step5 from "./components/step-5.vue";
import { ref } from "vue";

const currentStep = ref(1);
const addonsRendering = ref([]);

const nextStep = () => {
  currentStep.value++;
  console.log(currentStep.value);
};
const prevStep = () => {
  currentStep.value--;
  selectedAddons.value.splice(0, selectedAddons.value.length);
};
const change = () => {
  currentStep.value = 2;
  selectedAddons.value.splice(0, selectedAddons.value.length);
};

let switchBtn = ref(false);

let selectedPlan = ref();
let addonsTotal = ref();
let selectedAddons = ref([]);
let allTotal = ref();
let selectedPlanName = ref();
const plans = ref([
  {
    name: "Arcades",
    priceMonthly: 9,
    priceYearly: 90,
    img: "../assets/img/icon-arcade.svg",
    id: 1,
    active: false,
  },
  {
    name: "Advance",
    priceMonthly: 12,
    priceYearly: 120,
    img: "../assets/img/icon-advanced.svg",
    id: 2,
    active: false,
  },
  {
    name: "Pro",
    priceMonthly: 15,
    priceYearly: 150,
    img: "../assets/img/icon-pro.svg",
    id: 3,
    active: false,
  },
]);

const switchToggle = () => {
  switchBtn.value = !switchBtn.value;
  return switchBtn.value;
};
const handleSelectedPlan = function (plan) {
  plans.value.forEach((plan) => {
    plan.active = false;
  });

  if (switchBtn.value) {
    selectedPlan.value = plan.priceYearly;
    selectedPlanName.value = {
      name: plan.name,
      price: plan.priceYearly,
    };
  } else {
    selectedPlan.value = plan.priceMonthly;
    selectedPlanName.value = {
      name: plan.name,
      price: plan.priceMonthly,
    };
  }
  plan.active = !plan.active;
};
const addons = ref([
  {
    id: 1,
    name: "Pick Add-ons",
    desc: "Add-ons help enhance your gaming experience.",
    priceMonthly: 1,
    priceYearly: 10,
    active: false,
  },
  {
    id: 2,
    name: "online services",
    desc: "Access to multiplayer games",
    priceMonthly: 2,
    priceYearly: 12,
    active: false,
  },
  {
    id: 3,
    name: "larger storage",
    desc: "Extra 1TB of cloud save",
    priceMonthly: 2,
    priceYearly: 12,
    active: false,
  },
]);
let addonPrice = ref();
const handleSelectedAddons = function (event, addon) {
  if (event.target.checked) {
    addon.active = true;
    if (switchBtn.value) {
      addonPrice.value = {
        name: addon.name,
        price: addon.priceYearly,
      };
      selectedAddons.value.push(addonPrice.value);
    } else {
      addonPrice.value = {
        name: addon.name,
        price: addon.priceMonthly,
      };
      selectedAddons.value.push(addonPrice.value);
    }
  } else {
    addon.active = false;
    const index = selectedAddons.value.indexOf(addonPrice.value);
    selectedAddons.value.splice(index, 1);
  }
  addonsTotal.value = selectedAddons.value.reduce((sum, addon) => {
    return sum + addon.price;
  }, 0);

  allTotal.value = (selectedPlan.value || 12) + addonsTotal.value;
};

//total implementation
</script>
