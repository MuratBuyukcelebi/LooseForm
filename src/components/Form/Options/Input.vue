<template>
  <div class="input" :class="[`size--${size}`]">
    <div class="input__header" contentEditable="true">Header</div>
    <div class="input__content">
      <span class="input__content-textarea" contentEditable="true">placeholder</span>
      <button class="input__content-icon">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><!--! Font Awesome Pro 6.1.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2022 Fonticons, Inc. --><path d="M500.3 443.7l-119.7-119.7c27.22-40.41 40.65-90.9 33.46-144.7C401.8 87.79 326.8 13.32 235.2 1.723C99.01-15.51-15.51 99.01 1.724 235.2c11.6 91.64 86.08 166.7 177.6 178.9c53.8 7.189 104.3-6.236 144.7-33.46l119.7 119.7c15.62 15.62 40.95 15.62 56.57 0C515.9 484.7 515.9 459.3 500.3 443.7zM79.1 208c0-70.58 57.42-128 128-128s128 57.42 128 128c0 70.58-57.42 128-128 128S79.1 278.6 79.1 208z"/></svg>
      </button>
    </div>
  </div>
</template>

<script>

export default {
  name: "Input",
  props: {
    size: {
      type: String,
      default: "md",
      validator(value) {
        return ['sm', 'md', 'lg'].includes(value)
      },
    },
  }
}
</script>

<style scoped lang="scss">
.input {
  display: flex;
  flex-direction: column;
  gap: 16px;

  &__header {
    font-weight: bold;
    color: #fff;
  }
  &__content {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 16px;
    padding-left: 16px;
    padding-right: 16px;
    border-radius: 8px;
    border: 2px solid #42b883;
    word-break: break-word;

    &-textarea {
      color: #fff;
      display: flex;
      align-items: center;
      height: 52px;
      width: 100%;
      opacity: 0.5;
    }
    &-icon {
      flex: none;
      display: flex;
      align-items: center;
      justify-content: center;
      fill: #fff;
      background-color: transparent;
      border: none;
      outline: none;
      padding: 0;
    }
  }

  &.size {
    &--sm .input {
      &__header {
        font-size: 18px;
      }
      &__content {
        width: 260px;

        &-textarea {
          font-size: 14px;
        }
        &-icon {
          width: 18px;
          height: 18px;
        }
      }
    }
    &--md .input {
      &__header {
        font-size: 24px;
      }
      &__content {
        width: 340px;

        &-textarea {
          font-size: 16px;
        }
        &-icon {
          width: 24px;
          height: 24px;
        }
      }
    }
    &--lg .input {
      &__header {
        font-size: 32px;
      }
      &__content {
        width: 420px;

        &-textarea {
          font-size: 18px;
        }
        &-icon {
          width: 36px;
          height: 36px;
        }
      }
    }
  }
}
</style>