<template>
  <div class="header" :class="[`size--${size}`]">
    <div class="header__top" contentEditable="true">top</div>
    <div class="header__title" contentEditable="true">Header</div>
    <div class="header__description" contentEditable="true">description</div>
  </div>
</template>

<script>
export default {
  name: "Header",

  props: {
    size: {
      type: String,
      default: "md",
      validator(value) {
        return ['sm', 'md', 'lg'].includes(value)
      },
    }
  },
}
</script>

<style scoped lang="scss">
.header {
  display: flex;
  flex-direction: column;

  &__top {
    color: #bbbbbb;
    opacity: 0.7;
  }
  &__title {
    font-weight: bold;
    color: #fff;
  }
  &__description {
    color: #fff;
  }

  &.size {
    &--sm .header {
      &__top {
        font-size: 14px;
      }
      &__title {
        font-size: 24px;
      }
      &__description {
        font-size: 16px;
      }
    }
    &--md .header {
      &__top {
        font-size: 16px;
      }
      &__title {
        font-size: 36px;
      }
      &__description {
        font-size: 18px;
      }
    }
    &--lg .header {
      &__top {
        font-size: 18px;
      }
      &__title {
        font-size: 48px;
      }
      &__description {
        font-size: 25px;
      }
    }
  }

}
</style>