<template>
  <div class="step-1">
    <h5>personal info</h5>
    <p>Please provide your name, email address, and phone number.</p>

    <form>
      <span>Name</span>
      <input type="text" placeholder="e.g.stephen king" />
      <div class="label-wrapper">
        <label>Email</label>
        <label class="danger hidden">
          This field is required in mail format</label
        >
      </div>
      <input
        type="text"
        placeholder="e.g.olaniyansheyi1704@gmail.com"
        id="input-email"
      />
      <div class="label-wrapper">
        <label class="">Phone Number</label>
        <label class="danger hidden"> This field is required </label>
      </div>
      <input type="text" placeholder="e.g.+1 234 567 890" id="input-num" />
      <button class="next-step-1 btn-step-1" type="submit">Next step</button>
    </form>
  </div>
</template>
