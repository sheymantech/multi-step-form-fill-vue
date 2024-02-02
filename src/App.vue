<template>
  <img
    src="./assets/img/bg-sidebar-mobile.svg"
    class="hidden img-mobile"
    alt=""
  />
  <div class="container">
    <div class="row">
      <div class="col-lg-12 mx-auto body-cont">
        <div class="row">
          <div class="col-lg-4 me-lg-5">
            <img
              src="./assets/img/bg-sidebar-desktop.svg"
              class="img-desktop"
              alt=""
            />
          </div>
          <div class="col-lg-7 cont-wrapper mt-5 ms-lg-3">
            <step1 v-if="currentStep === 1" @next="nextStep" />
            <step2 v-if="currentStep === 2" @next="nextStep" @prev="prevStep" />
            <step3 v-if="currentStep === 3" @next="nextStep" @prev="prevStep" />
            <step4 v-if="currentStep === 4" @next="nextStep" @prev="prevStep" />
            <step5 v-if="currentStep === 5" @next="nextStep" @prev="prevStep" />
          </div>
        </div>

        <div class="progress-wrapper text-white">
          <div class="progress-bar">
            <div class="progress-bar-box box-1 active">1</div>
            <div class="progress-bar-cont">
              <p>STEP 1</p>
              <h6>YOUR INFO</h6>
            </div>
          </div>
          <div class="progress-bar">
            <div class="progress-bar-box box-2">2</div>
            <div class="progress-bar-cont">
              <p>STEP 2</p>
              <h6>HOST PLAN</h6>
            </div>
          </div>
          <div class="progress-bar">
            <div class="progress-bar-box box-3">3</div>
            <div class="progress-bar-cont">
              <p>STEP 3</p>
              <h6>ADD-ONS</h6>
            </div>
          </div>
          <div class="progress-bar">
            <div class="progress-bar-box box-4">4</div>
            <div class="progress-bar-cont">
              <p>STEP 4</p>
              <h6>SUMMARY</h6>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="p-5 copy-write">
    Challenge by
    <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
      >Frontend Mentor</a
    >. Coded by <a href="https://twitter.com/olaniyanoe1704">olaniyan sheyi</a>.
  </div>
</template>

<script setup>
import step1 from "./components/step-1.vue";
import step2 from "./components/step-2.vue";
import step3 from "./components/step-3.vue";
import step4 from "./components/step-4.vue";
import step5 from "./components/step-5.vue";
import { ref } from "vue";

const currentStep = ref(1);
</script>
