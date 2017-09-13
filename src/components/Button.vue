<template>
  <button :class="classes" :type="nativeType ":disabled="disabled">
    <slot></slot>
  </button>
</template>

<script>
  export default {
    props: {
      type: {
        type: String,
        required: true
      },
      nativeType: {
        type: String,
        default: 'button'
      },
      plain: {
        type: Boolean,
        default: false
      },
      disabled: {
        type: Boolean,
        default: false
      }
    },
    computed: {
      classes() {
        return [
          `button--${this.type}`,
          {
            'is-plain': this.plain,
            'is-disabled': this.disabled
          }
        ];
      }
    }
  }
</script>
<style lang="scss">
  .button {
    background: red;

    &.is-disabled {
      opacity: .4;
      cursor: not-allowed;
    }
  }
  .button--submit {
    @extend .button;
  }
  .button--cancel {
    @extend .button;
    color: #fff;
    background: green;
  }

</style>
