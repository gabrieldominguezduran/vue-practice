<template>
  <div class="ctr">
    <transition name="fade" mode="out-in">
      <questions
        v-if="questionsAnswered < questions.length"
        :questions="questions"
        :questionsAnswered="questionsAnswered"
        @question-answered="questionAnswered"
      />
      <result
        v-else
        :results="results"
        :totalCorrect="totalCorrect"
      />
    </transition>
    <button
      type="button"
      class="reset-btn"
      @click.prevent="reset"
      v-if="questionsAnswered === questions.length"
    >
      Reset
    </button>
  </div>
</template>

<script>
import Questions from "@/components/Quiz/Questions.vue";
import Result from "@/components/Quiz/Result.vue";

export default {
  components: {
    Questions,
    Result
  },
  data() {
    return {
      questionsAnswered: 0,
      totalCorrect: 0,
      questions: [
        {
          q: "What is 2 + 2?",
          answers: [
            {
              text: "4",
              is_correct: true
            },
            {
              text: "3",
              is_correct: false
            },
            {
              text: "Fish",
              is_correct: false
            },
            {
              text: "5",
              is_correct: false
            }
          ]
        },
        {
          q: "How many letters are in the word \"Banana\"?",
          answers: [
            {
              text: "5",
              is_correct: false
            },
            {
              text: "7",
              is_correct: false
            },
            {
              text: "6",
              is_correct: true
            },
            {
              text: "12",
              is_correct: false
            }
          ]
        },
        {
          q: "Find the missing letter: C_ke",
          answers: [
            {
              text: "e",
              is_correct: false
            },
            {
              text: "a",
              is_correct: true
            },
            {
              text: "i",
              is_correct: false
            }
          ]
        },
      ],
      results: [
        {
          min: 0,
          max: 2,
          title: "Try again!",
          desc: "Do a little more studying and you may succeed!"
        },
        {
          min: 3,
          max: 3,
          title: "Wow, you're a genius!",
          desc: "Studying has definitely paid off for you!"
        }
      ]
    };
  },
  methods: {
    questionAnswered(isCorrect) {
      if (isCorrect) {
        this.totalCorrect++;
      }

      this.questionsAnswered++;
    },
    reset() {
      this.questionsAnswered = 0;
      this.totalCorrect = 0;
    },
  }
};
</script>

<style scoped>

.ctr {
  margin: 0 auto;
  max-width: 600px;
  width: 100%;
  box-sizing: border-box;
  position: relative;
}

.reset-btn {
  background-color: #ff6372;
  border: 0;
  font-size: 22px;
  color: #fff;
  padding: 10px 25px;
  margin: 10px auto;
  display: block;
}


.reset-btn:active, .reset-btn:focus, .reset-btn:hover {
  border: 0;
  outline: 0;
}

</style>
