<template>
  <WakeupQuestions />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import WakeupQuestions from "../components/WakeupQuestions.vue";

@Options({
  components: { WakeupQuestions },
})
export default class Home extends Vue {}
</script>
