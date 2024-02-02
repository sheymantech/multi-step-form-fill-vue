<template>
  <div class="step-2">
    <h5>Select your plan</h5>
    <p>you have the option of monthly or yearly billing.</p>
    <div class="row plans-cont">
      <div
        data-price-yearly="90"
        data-price-monthly="9"
        class="col-lg-3 col-4 plans ms-3"
      >
        <img src="./img/icon-arcade.svg" alt="" />
        <div class="plan-cont-wrapper">
          <h4>Arcade</h4>
          <p class="price-year1">$9/mo</p>
          <h6 class="hidden year-plan">2 months free</h6>
        </div>
      </div>
      <div
        data-price-yearly="120"
        data-price-monthly="12"
        class="col-lg-3 col-4 ms-3 plans"
      >
        <img src="./img/icon-advanced.svg" alt="" />
        <div class="plan-cont-wrapper">
          <h4>Advanced</h4>
          <p class="price-year2">$12/mo</p>
          <h6 class="hidden year-plan">2 months free</h6>
        </div>
      </div>
      <div
        data-price-yearly="150"
        data-price-monthly="15"
        class="col-lg-3 ms-3 col-4 plans"
      >
        <img src="./img/icon-pro.svg" alt="" />
        <div class="plan-cont-wrapper">
          <h4>Pro</h4>
          <p class="price-year3">$15/mo</p>
          <h6 class="hidden year-plan">2 months free</h6>
        </div>
      </div>
    </div>
    <div class="plan-duration">
      <h6>monthly</h6>
      <div class="switch-cont">
        <div class="switch-toggle"></div>
      </div>
      <h6>yearly</h6>
    </div>
    <button class="next-step-2 btn-step-2 mt-5">Next step</button>
    <button class="go-back-step-2 btn-back-2 mt-5">Go Back</button>
  </div>
</template>
