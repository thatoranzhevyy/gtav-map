<template>
  <div>
    <NuxtLink
      :to="to"
      class="tracking-wide font-medium py-2 transition inline-flex items-center justify-center whitespace-nowrap hover:bg-primaryDark focus:outline-none focus-visible:bg-primaryDark"

    >
      {{ label }}
    </NuxtLink>
  </div>
</template>
<script>
export default {
  // props: ['to', 'label', 'class', 'disabled'],
  props: {
    to: {
      type: String,
      default: ''
    },
    exact: {
      type: Boolean,
      default: true
    },
    blank: {
      type: Boolean,
      default: false
    },
    label: {
      type: String,
      default: ''
    },
    icon: {
      type: String,
      default: ''
    },
    svg: {
      type: String,
      default: ''
    },
    color: {
      type: String,
      default: 'green'
    },
    disabled: {
      type: Boolean,
      default: false
    },
    reverse: {
      type: Boolean,
      default: false
    },
    rounded: {
      type: Boolean,
      default: false
    },
    large: {
      type: Boolean,
      default: false
    },
    outline: {
      type: Boolean,
      default: false
    },
    shortcut: {
      type: Array,
      default: () => []
    },
    filled: {
      type: Boolean,
      default: false
    }
  }
}
</script>
<style>
a {
  @apply inline-flex;
  @apply text-current;
  @apply no-underline;
  @apply outline-none;
  @apply transition;
}

</style>
