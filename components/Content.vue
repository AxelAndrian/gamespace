<template>
  <b-container>
    <b-row>
      <b-col cols="12" class="contents">
        <img
          src="@/assets/images/Logo/gamespace-01.svg"
          alt
          class="img-fluid"
          style="width: 200px;"
        >
      </b-col>
      <b-col cols="12" class="contents">
        <h1 class="text__white text-center">
          {{ title }}
        </h1>
      </b-col>
      <b-col cols="12" class="description-content">
        <slot name="content" />
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: '',
      required: true
    }
  }
}
</script>
