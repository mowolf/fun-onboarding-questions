<template>
  <div class="container animated-gradient">
    <div class="question">
      <p>{{ selectedQuestion }}</p>
    </div>
    <div class="button-container" @click="getRandomQuestion()">
      <button>
        <div class="button-content">
          ⁉️
        </div>
      </button>
    </div>
    <a
      href="https://github.com/mowolf/fun-onboarding-questions"
      class="github-icon"
    >
      <img
        src="~/assets/img/github.svg"
        alt="Github Icon"
        height="30"
        width="30"
      />
    </a>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedQuestion: undefined,
      questions: [
        "What did you learn in the last week?",
        "What was the worst food you ever had?",
        "Whats the best item you bougth in the last year/month?",
        "Whats your dream assignement/job?",
        "What is the one thing you’d most like to change about the world?",
        "If happiness was the national currency, what kind of work would make you rich?",
        "If the average human life span was 40 years, how would you live your life differently?",
        "If you could offer a newborn child only one piece of advice, what would it be?",
        "What’s something you know you do differently than most people?",
        "What one thing have you not done that you really want to do? What’s holding you back?",
        "If you had to move to a different place, where would you move and why?",
        "Would you rather lose all of your old memories, or never be able to make new ones?",
        "What is your happiest childhood memory? What makes it so special?",
        "At what time in your recent past have you felt most passionate and alive?",
        "If you were given a choice between being given great wisdom or great wealth, which would you choose? Why?",
        "If you were going to a deserted island and could only take three things with you, what would you take? Why?",
        "If you knew that everyone you know was going to die tomorrow, who would you visit today?",
        "What would you do differently if you knew nobody would judge you?",
        "What is the one thing you’d most like to change about your life?",
        "Are you making decisions for yourself, or are you letting others make them for you?",
        "If you were granted three wishes from a genie what would you want? (normal genie rules apply)",
        "When you were growing up what did you want to become in life?",
        "What are you most proud of? Why?",
        "Which is the trait you love the most and least about yourself?",
        "Which character in a book or movie best describes who you are?",
        "Describe yourself in a single word/phrase.",
        "Which song best fits your image and why?",
        "What is the one thing that you would want your children to learn about life?",
        "If you could travel back in time and meet yourself as a 10 year old what advice would you want to give yourself?",
        "If you had only 24 hours to live, what would you do?",
        "If you could stop a bad habit that you have, what would you stop?",
        "If you could do any job, what would you like to do?",
        "If you had to choose, would you give up your sight or your hearing? Why?",
        "If you could hear what someone is thinking for a day, who would you choose? Why that person?",
        "If you could meet any person, dead or alive, who would it be and why?",
        "If you could travel back in time, where would you go?",
        "If you could be invisible for a day what would you do and why?",
        "If you could change one thing about yourself, what would it be? Why?",
        "If you could choose how you were going to die, what would you choose?",
        "If you had everyone in the worlds undivided attention for 20 minutes, what would you tell us?",
        "When you’re 90 years old, what will matter most to you?",
        "What do you regret most so far in life? How can you apply the lesson you learned from that regret to your life today?",
        "Are you holding onto something that you need to let go of? If so what? And why haven’t you let go of it?",
        "What activities make you lose track of time?",
        "What lies do you often hear people tell? What lie do you often tell?",
        "What are you most grateful for?",
        "What did life teach you yesterday?",
        "What is your “go-to” joke or funny story?",
        "What conversation do you know you need to have, but you’re avoiding?",
        "What is something you seriously take for granted?",
        "When you think of home, what immediately comes to mind?",
        "What can you do today that you couldn’t do a year ago?",
        "What is something you hate, but wish you loved? Why?",
        "What is something that you think a lot of people misunderstand that you know a lot about?",
        "What is something you’ve learned recently?",
        "What is something someone said that forever changed your way of thinking?",
        "What idea and/or thought has most influenced your life?",
        "What part of your life do you wish friends or family were more curious about?",
        "What’s the best recent conversation you’ve had? What made it so memorable?",
        "When does a place become a home for you? Why’s that?",
        "When and where do you most find peace?",
        "Is there anyone in your life you need to forgive? If so, why?",
        "How would you describe your relationship with art?",
        "Who’s been an influential role model in your life?",
        "Who’s a friend you’ve recently been appreciative of? Why was that?",
        "What’s an important lesson you’ve learned from a recent failure?",
        "When was the last time you were inspired? What was it that inspired you?",
        "When in your life have you felt most understood?",
        "Where do you turn to when you’re looking for inspiration?",
        "What is a rule you live your life by? When have you most recently applied this rule?",
        "What’s a compliment you’ve been given most recently that you’re proud of? What made it so meaningful?",
        "What’s something you’ve recently learned about yourself?",
        "Is there anything you’re willing to die for? If so, why?",
        "What do you look for in a friend?",
        "What’s something about your future that excites you? Why?",
        "What part of you life story are you most proud of?",
        "Who is your favorite artist? Why?",
        "What’s something beautiful you’ve seen recently?",
        "What’s your story?",
        "What’s the most expensive thing you’ve ever stolen?",
        "What is your present state of mind?",
        "What absolutely excites your right now?",
        "What book has influenced you the most?",
        "If you could do anything you wanted tonight (anywhere, for any amount of money), what would you do and why?",
        "If you had the opportunity to meet one person you haven’t met who would it be, why and what would you talk about?",
        "What’s the most important thing i should know about you?",
        "What movie is your favorite guilty pleasure, and why?",
        "What do you think is the driving force in your life?",
        "When and where were you happiest in your life?",
        "What is this chapter of your life called?",
        "What is the most uplifting thing you think is happening in the world right now? What is the most tragic thing?",
        "What do you understand today about your life that you didn’t understand a year ago?",
        "What smell brings back great memories?",
        "Who had the biggest impact on the person you have become?",
        "What’s the best gift you’ve ever gotten? What made it so special?",
        "How should success be measured? By that measurement, who is the most successful person you know?",
        "If you could teach me anything, what would it be?",
        "What is one thing you’ve done in your life that you wish you could undo?",
        "What have you given up on?",
        "What is your “secret- sauce” that makes you, you?",
        "What would you be willing to reduce your life expectancy by 10 years for?",
        "If you could invite anyone in the world to dinner, who would it be?",
        "Would you like to be famous? In what way?",
        "Before making a telephone call, do you ever rehearse what you are going to say? Why?",
        "What would constitute a “perfect” day for you?",
        "If you were able to live to the age of 90 and retain either the mind or body of a 30-year-old for the last 60 years of your life, which would you want?",
        "If you could change anything about the way you were raised, what would it be?",
        "If you could wake up tomorrow having gained any one quality or ability, what would it be?",
        "If a crystal ball could tell you the truth about yourself, your life, the future or anything else, what would you want to know?",
        "What is the greatest accomplishment of your life?",
        "If you knew that in one year you would die suddenly, would you change anything about the way you are now living? Why?",
        "What does friendship mean to you?",
        "What roles do love and affection play in your life?",
        "How close and warm is your family? Do you feel your childhood was happier than most other people’s?",
        "How do you feel about your relationship with your mother?",
        "When did you last cry in front of another person? By yourself?",
        "What, if anything, is too serious to be joked about?",
        "If you were to die this evening with no opportunity to communicate with anyone, what would you most regret not having told someone? Why haven’t you told them yet?",
        "Of all the people in your family, whose death would you find most disturbing? Why?",
        "What’s been the most embarrassing moment of your life?",
        "Who’s someone you’ve been thinking about often recently? Why?",
        "What’s an interesting thing you recently googled?",
        "If you knew you could not fail, what is the one thing you’d like to accomplish?",
        "If the whole world were listening, what would you say?",
        "If you could be an other colleague for one day, who would you be?",
        "What's the first thing you would buy if you suddenly became a billionaire?",
        "What's a hobby project you would like to do at some point?",
        "What is your proudest accomplishment?",
        "What is your proudest accomplishment?",
        "What is a superpower you desire? The catch is that the next person in the question chain has to decide the catch to your superpower!",
        "What's the most interesting thing you can see out of your office or kitchen window?",
        "Where do you see yourself in 10 years?",
        "What is your favorite family holiday tradition?",
        "Is there anything you wished would come back into fashion?  ",
        "If you had a warning label, what would yours say?",
        "What's the most daring thing you've ever done?",
        "What was the last book you read?",
        "What's the most unusual thing you've ever eaten?",
        "Do you collect anything?",
        "What is your favorite thing about your career?"
      ]
    };
  },
  created() {
    this.getRandomQuestion();
  },
  methods: {
    getRandomQuestion() {
      this.selectedQuestion = this.questions[
        Math.floor(Math.random() * this.questions.length)
      ];
    }
  }
};
</script>

<style scoped>
.github-icon {
  position: absolute;
  top: 0;
  right: 0;
  padding: 10px;
}

.question {
  margin-top: 40vh;
  transform: translateY(-50%);
  font-size: max(4.5vw, 4.5vh);
  margin-left: 10%;
  margin-right: 10%;
  font-weight: 700;
  /* text-shadow: 0px 0px transparent;
  background: -webkit-linear-gradient(45deg, tomato, gold);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-box-decoration-break: clone; */
}

.button-container {
  position: absolute;
  bottom: 10%;
  left: 50%;
  transform: translateX(-50%);
}

button {
  border: none;
  transition: 0.2s;
  cursor: pointer;
  font-weight: bold;
  background: none;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  padding: 10px;
}

.button-content {
  box-shadow: 0 0 8px rgb(52, 52, 52);
  border-radius: 50px;
  padding: 15px 32px;
}

button:hover .button-content {
  -webkit-animation: AnimationName 6s ease infinite;
  -moz-animation: AnimationName 6s ease infinite;
  -o-animation: AnimationName 6s ease infinite;
  animation: AnimationName 6s ease infinite;
  background: linear-gradient(45deg, #ff0000, #ffd900, #2bff00);
  background-size: 800% 800%;
}

button:hover {
  transform: scale(1.1, 1.1);
}

button:active {
  filter: drop-shadow(0 0 2px #7272726b);
  color: black;
  transform: translate(2px, 2px);
}

.container {
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  position: absolute;
  text-align: center;
  overflow: hidden;
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
  0% {
    background-position: 43% 0%;
  }
  50% {
    background-position: 58% 100%;
  }
  100% {
    background-position: 43% 0%;
  }
}
@-moz-keyframes AnimationName {
  0% {
    background-position: 43% 0%;
  }
  50% {
    background-position: 58% 100%;
  }
  100% {
    background-position: 43% 0%;
  }
}
@-o-keyframes AnimationName {
  0% {
    background-position: 43% 0%;
  }
  50% {
    background-position: 58% 100%;
  }
  100% {
    background-position: 43% 0%;
  }
}
@keyframes AnimationName {
  0% {
    background-position: 43% 0%;
  }
  50% {
    background-position: 58% 100%;
  }
  100% {
    background-position: 43% 0%;
  }
}

img {
  transition: 0.5s;
}
img:hover {
  filter: drop-shadow(2px 2px 10px white);
  transform: translate(-2px, -2px);
}
</style>
