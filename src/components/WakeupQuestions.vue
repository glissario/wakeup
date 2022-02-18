<template>
  <main>
    <h1><strong>#Aufwachfragen</strong> des Tages</h1>
    <h2>{{ compareDate + today.getFullYear() }}</h2>
    <WakeupQuestion
      v-for="(question, i) in filteredQuestion"
      :key="i"
      :question="question"
    />
    <p>inspired by Udo Wiegärtner</p>
  </main>
</template>

<script>
import list from "../assets/wakeup.json";
import WakeupQuestion from "../components/WakeupQuestion.vue";
export default {
  name: "WakeupQuestions",
  components: { WakeupQuestion },
  data() {
    return {
      theList: list.wakeupQuestions,
      today: new Date(),
      compareDate: "",
      filteredQuestion: [],
    };
  },
  beforeMount() {
    let month = (this.today.getMonth() + 1).toString();
    month.length === 1 ? (month = "0" + month) : month;
    this.compareDate = this.today.getDate() + "/" + month + "/";
    this.theList.forEach((element) => {
      element.date.includes(this.compareDate)
        ? this.filteredQuestion.push(element)
        : this.filteredQuestion;
    });
  },
};
</script>

<style>
main {
  margin: 0 auto;
  width: 18rem;
  background-color: #023e8a;
  padding: 2rem;
  color: white;
}
</style>
