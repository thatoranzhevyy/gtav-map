<template>
  <div>
    <header class="flex justify-between space-x-2 flex-1 py-1 px-1 items-center">
      <div class="space-x-2 inline-flex items-center">
        <ButtonSecondary
          class="tracking-wide !font-bold !text-secondaryDark"
          label="index"
          to="/"
        />
        <ButtonSecondary
          class="tracking-wide !font-bold !text-secondaryDark"
          label="about"
          to="/about"
        />
        <button
          class="py-2 px-3 bg-green-500 rounded shadow-md text-white uppercase"
          @click="changeMode"
        >
          Button
        </button>
      </div>
      <div class="space-x-2 inline-flex items-center">
        <ButtonPrimary
          class="tracking-wide !font-bold !text-secondaryDark"
          label="testPrimary"
          to="/"
        />
      </div>
    </header>
  </div>
</template>
<script>
export default {
  methods: {
    changeMode () {
      this.$colorMode.preference =
        this.$colorMode.preference === 'light' ? 'dark' : 'light'
    }
  }
}
</script>
