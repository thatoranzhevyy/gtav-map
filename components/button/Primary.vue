<template>
  <div>
    <a
      class="tracking-wide font-medium py-2 transition inline-flex items-center justify-center whitespace-nowrap hover:bg-primaryDark focus:outline-none focus-visible:bg-primaryDark"
      :class="[
        color
          ? `text-${color}-800 bg-${color}-200 hover:(text-${color}-900 bg-${color}-300) focus-visible:(text-${color}-900 bg-${color}-300)`
          : `text-accentContrast bg-accent hover:bg-accentDark focus-visible:bg-accentDark`,
        label ? 'px-4' : 'px-2',
        rounded ? 'rounded-full' : 'rounded',
        { 'opacity-75 cursor-not-allowed': disabled },
        { 'pointer-events-none': loading },
        { 'px-6 py-4 text-lg': large },
        { 'shadow-lg hover:shadow-xl': shadow },
        {
          'text-white bg-gradient-to-tr from-gradientFrom via-gradientVia to-gradientTo':
            gradient,
        },
        {
          'border border-accent hover:border-accentDark focus-visible:border-accentDark':
            outline,
        },
      ]"
      :disabled="disabled"
      tabindex="0"
    >
      {{ label }}
    </a>
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
      default: ''
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
