<template>
  <div class="step-3">
    <h5>Pick Add-ons</h5>
    <p>Add-ons help enhance your gaming experience.</p>
    <div class="row">
      <div
        class="col-lg-8 add-ons-wrapper mt-3"
        v-for="addon in addons"
        :key="addon.id"
      >
        <div class="row cont-fill">
          <div class="add-ons-content-main col-10">
            <input type="checkbox" class="service" />
            <div class="add-ons-content-child mt-3">
              <h6>{{ addon.name }}</h6>
              <p>{{ addon.desc }}</p>
            </div>
          </div>
          <div class="col-2">
            <h6 class="price-addons-1">
              {{
                switchChecker
                  ? `$${addon.priceYearly}/Yr`
                  : `$${addon.priceMonthly}/Mo`
              }}
            </h6>
          </div>
        </div>
      </div>
    </div>
    <button class="next-step-3 btn-step-3 mt-5" @click="nextStep">
      Next step
    </button>
    <button class="go-back-step-3 btn-back-3 mt-5" @click="prevStep">
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
  switchChecker: {
    type: Boolean,
    required: true,
  },
});

const addons = ref([
  {
    id: 1,
    name: "Pick Add-ons",
    desc: "Add-ons help enhance your gaming experience.",
    priceMonthly: 1,
    priceYearly: 10,
  },
  {
    id: 2,
    name: "online services",
    desc: "Access to multiplayer games",
    priceMonthly: 2,
    priceYearly: 12,
  },
  {
    id: 3,
    name: "larger storage",
    desc: "Extra 1TB of cloud save",
    priceMonthly: 2,
    priceYearly: 12,
  },
]);
</script>
