<template>
  <article>
    <p>Nr: {{ question.index }}, {{ year }}</p>

    <p>
      <strong>{{ question.question.replace("<br />","") }} </strong>
    </p>
    <a :href="question.url">
      <img target="_blank" src="@/assets/twitter-icon.png" /> Zur Diskussion auf
      Twitter</a
    >
  </article>
</template>

<script>
export default {
  name: "WakeupQuestion",
  data() {
    return {
      year: this.question.date.slice(
        this.question.date.length - 4,
        this.question.date.length
      ),
    };
  },
  props: {
    question: {
      date: String,
      index: String,
      question: String,
      url: String,
    },
  },
};
</script>

<style>
article {
  box-sizing: border-box;
  background-color: white;
  color: #023e8a;
  width: 100%;
  margin-bottom: 1.75rem;
  border: 0.25rem solid #03045e;
  padding: 1rem 0.75rem;
}

a {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  color: #023e8a;
  font-size: 1rem;
  text-decoration: none;
}

img {
  object-fit: contain;
  height: 1rem;
  margin-right: 0.25rem;
}
</style>
