<template>
  <div class="step-3">
    <h5>Pick Add-ons</h5>
    <p>Add-ons help enhance your gaming experience.</p>
    <div class="row">
      <div class="col-lg-8 add-ons-wrapper mt-3">
        <div class="row cont-fill">
          <div class="add-ons-content-main col-10">
            <input
              data-addons-monthly="1"
              data-addons-yearly="10"
              type="checkbox"
              class="service"
            />
            <div class="add-ons-content-child mt-3">
              <h6>online service</h6>
              <p>Access to multiplayer games</p>
            </div>
          </div>
          <div class="col-2">
            <h6 class="price-addons-1">+$1/mo</h6>
          </div>
        </div>
      </div>

      <div class="col-lg-8 add-ons-wrapper mt-3">
        <div class="row cont-fill">
          <div class="add-ons-content-main col-10">
            <input
              data-addons-monthly="2"
              data-addons-yearly="20"
              type="checkbox"
              class="larger-storage"
            />
            <div class="add-ons-content-child mt-3">
              <h6>Larger Storage</h6>
              <p>Extra 1TB of cloud save</p>
            </div>
          </div>
          <div class="col-2">
            <h6 class="price-addons-2">+$2/mo</h6>
          </div>
        </div>
      </div>
      <div class="col-lg-8 add-ons-wrapper mt-3">
        <div class="row cont-fill">
          <div class="add-ons-content-main col-10">
            <input
              data-addons-monthly="2"
              data-addons-yearly="20"
              type="checkbox"
              class="customize"
            />
            <div class="add-ons-content-child mt-3">
              <h6>Custumizable profile</h6>
              <p>Custom theme on your profile</p>
            </div>
          </div>
          <div class="col-2">
            <h6 class="price-addons-3">+$2/mo</h6>
          </div>
        </div>
      </div>
    </div>
    <button class="next-step-3 btn-step-3 mt-5">Next step</button>
    <button class="go-back-step-3 btn-back-3 mt-5">Go Back</button>
  </div>
</template>
