<template>
  <div class="container animated-gradient">
    <div class="question">
      <p>{{ selectedQuestion }}</p>
    </div>
    <div class="button-container" @click="getRandomQuestion()">
      <button>
        Get new question!
      </button>
    </div>
    <a href="https://github.com/mowolf/fun-onboarding-questions" class="github-icon">
      <img src="~/assets/img/github.svg" alt="Github Icon" height="30" width="30">
    </a>
  </div>
</template>

<script>
export default {
  data () {
    return {
      selectedQuestion: undefined,
      questions: ['What did you learn in the last week?', 'What was the worst food you ever had?']
    }
  },
  created () {
    this.getRandomQuestion()
  },
  methods: {
    getRandomQuestion () {
      console.log('as')
      this.selectedQuestion = this.questions[
        Math.floor(Math.random() * this.questions.length)
      ]
    }
  }
}
</script>

<style scoped>
.github-icon {
 position: absolute;
 top: 0;
 right: 0;
 padding: 10px
}

.question {
  margin-top: 40vh;
  transform: translateY(-50%);
  font-size: 4em;
}

button {
  cursor: pointer;
  font-weight: bold;
  background: none;
  border: none;
  border-radius: 50px;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  box-shadow: 1px 1px 5px black;
}

button:hover {
  background: linear-gradient(270deg, #ff0000, #00ff91, #ffd900, #ff0000);
  background-size: 400% 400%;
  -webkit-animation: AnimationName 3s ease infinite;
  -moz-animation: AnimationName 3s ease infinite;
  -o-animation: AnimationName 3s ease infinite;
  animation: AnimationName 3s ease infinite;
}

button:active {
  filter: drop-shadow(0 0 2px #7272726b);
  color: black;
  transform: translate(2px, 2px);
  background: linear-gradient(270deg, #ff0000, #00ff91, #ffd900, #ff0000);
  background-size: 400% 400%;
  -webkit-animation: AnimationName 3s ease infinite;
  -moz-animation: AnimationName 3s ease infinite;
  -o-animation: AnimationName 3s ease infinite;
  animation: AnimationName 3s ease infinite;
}

.container {
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  position: absolute;
  text-align: center;
}

.animated-gradient {
  background: linear-gradient(270deg, #ff0000, #00ff91, #9800ff, #c1ff00);
  background-size: 800% 800%;
  -webkit-animation: AnimationName 30s ease infinite;
  -moz-animation: AnimationName 30s ease infinite;
  -o-animation: AnimationName 30s ease infinite;
  animation: AnimationName 30s ease infinite;
}

@-webkit-keyframes AnimationName {
    0%{background-position:43% 0%}
    50%{background-position:58% 100%}
    100%{background-position:43% 0%}
}
@-moz-keyframes AnimationName {
    0%{background-position:43% 0%}
    50%{background-position:58% 100%}
    100%{background-position:43% 0%}
}
@-o-keyframes AnimationName {
    0%{background-position:43% 0%}
    50%{background-position:58% 100%}
    100%{background-position:43% 0%}
}
@keyframes AnimationName {
    0%{background-position:43% 0%}
    50%{background-position:58% 100%}
    100%{background-position:43% 0%}
}

</style>
