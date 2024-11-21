<script setup>
  defineProps(['title'])
</script>

<template>
    <button
    :class="['button-3', variant, size]"
    role="button"
    :disabled="disabled"
    @click="handleClick"
  >
  {{ title }} 
  </button>
</template>

<style>
.button-3 {
  appearance: none;
  background-color: #2ea44f;
  border: 1px solid rgba(27, 31, 35, .15);
  border-radius: 6px;
  box-shadow: rgba(27, 31, 35, .1) 0 1px 0;
  box-sizing: border-box;
  color: #fff;
  cursor: pointer;
  display: inline-block;
  font-size: 14px;
  font-weight: 600;
  line-height: 20px;
  padding: 6px 16px;
  position: relative;
  text-align: center;
  text-decoration: none;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  vertical-align: middle;
  white-space: nowrap;
  margin: 10px;
}

.button-3:focus:not(:focus-visible):not(.focus-visible) {
  box-shadow: none;
  outline: none;
}

.button-3:hover {
  background-color: #2c974b;
}

.button-3:focus {
  box-shadow: rgba(46, 164, 79, .4) 0 0 0 3px;
  outline: none;
}

.button-3:disabled {
  background-color: #94d3a2;
  border-color: rgba(27, 31, 35, .1);
  color: rgba(255, 255, 255, .8);
  cursor: default;
}

.button-3:active {
  background-color: #298e46;
  box-shadow: rgba(20, 70, 32, .2) 0 1px 0 inset;
}
</style>

<script>
  export default {
    name: "ButtonComponent",
    props: {
      // Props for customization
      variant: {
        type: String,
        default: "primary", // Options: primary, secondary, danger, etc.
      },
      size: {
        type: String,
        default: "medium", // Options: small, medium, large
      },
      disabled: {
        type: Boolean,
        default: false,
      },
    },
    methods: {
      handleClick(event) {
        // Emit a click event unless the button is disabled
        if (!this.disabled) {
          this.$emit("mouseup", event);
        }
      },
    },
  };

</script>