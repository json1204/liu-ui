<template>
  <button
    @click="$emit('click')"
    class="l__button"
    :disabled="disabled"
    :class="[
    'l__button--'+type,
    {'is-plain': plain, 'is-disabled': disabled, 'is-round': round},
    'l__button--size-'+size
    ]"
  >
    <i v-if="icon !== ''" :class="icon"></i>
    <slot></slot>
  </button>
</template>
<script>
  export default{
    name: 'LButton',
    props: {
      type: {
        type: String,
        default: 'default'
      },
      size: {
        type: String,
        default: 'default'
      },
      icon: {
        type: String,
        default: ''
      },
      plain: Boolean,
      disabled: Boolean,
      round: Boolean
    },
    data () {
      return {
        msg: 'button'
      }
    }
  }
</script>
