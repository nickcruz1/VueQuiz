<!-- This app will be an interactive/well designed quiz app... User is asked a series of questions.. if answer correctly then move onto next page. Use alot of conditional rendering -->
<template>
  <div id="app">
    <h2>Quiz App</h2>
    
 <!-- Start Of Quiz (This starts the quiz off) Btn -->
    <button class="startQuizBtn" :class="{clicked: clickMe, notClicked: notClick}" @click="question = 'Q1'">Start Quiz</button>
 <!-- Use Conditional Class Binding -->
   <!-- Use V-for to display all wrong answers for each view -->

 <!-- Start of Quiz - Question #1 -->
    <div class="questionFormat" v-if="question === 'Q1'">
    <div>
      <h2>Question 1</h2>
     
        <p>What is my name?</p>

        <a :class="{wrong: wrongAnswer}" @click="wrongAnswer = !wrongAnswer" href="#">Answer 1</a>
        <a :class="{wrong: wrongAnswer}" @click="wrongAnswer = !wrongAnswer" href="#">Answer 2</a>
        <a @click="question = 'Q2'" href="#">Answer 3</a>
        <a :class="{wrong: wrongAnswer}" @click="wrongAnswer = !wrongAnswer" href="#">Answer 4</a>
      </div>
</div>

  <!-- Question #2 -->
  <div class="questionFormat" v-if="question === 'Q2'">
    <div>
      <h2>Question 2</h2>
     
        <p>What kind of a developer am I?</p>

        <a :class="{wrong: wrongAnswer}" @click="wrongAnswer = !wrongAnswer" href="#">Answer 1</a>
        <a :class="{wrong: wrongAnswer}" @click="wrongAnswer = !wrongAnswer" href="#">Answer 2</a>
        <a @click="question = 'Q3'" href="#">Answer 3</a>
        <a :class="{wrong: wrongAnswer}" @click="wrongAnswer = !wrongAnswer" href="#">Answer 4</a>
      </div>
</div>

  <!-- Question #3 -->
      <div class="questionFormat" v-if="question === 'Q3'">
    <div>
      <h2>Question 3</h2>
     
        <p>Where Do I live?</p>

        <a :class="{wrong: wrongAnswer}" @click="wrongAnswer = !wrongAnswer" href="#">Answer 1</a>
        <a :class="{wrong: wrongAnswer}" @click="wrongAnswer = !wrongAnswer" href="#">Answer 2</a>
        <a @click="question = 'Q4'" href="#">Answer 3</a>
        <a :class="{wrong: wrongAnswer}" @click="wrongAnswer = !wrongAnswer" href="#">Answer 4</a>
      </div>
</div>

 <!-- Question #4 -->
      <div class="questionFormat" v-if="question === 'Q4'">
    <div>
      <h2>Question 4</h2>
     
        <p>How long have I been coding?</p>

        <a :class="{wrong: wrongAnswer}" @click="wrongAnswer = !wrongAnswer" href="#">Answer 1</a>
        <a :class="{wrong: wrongAnswer}" @click="wrongAnswer = !wrongAnswer" href="#">Answer 2</a>
        <a @click="question = 'finish'" href="#">Answer 3</a>
        <a :class="{wrong: wrongAnswer}" @click="wrongAnswer = !wrongAnswer" href="#">Answer 4</a>
      </div>
</div>

<div class="questionFormat" v-if="question === 'finish'">
    <h2>CONGRATULATIONS!!!</h2>
    
       <p>You've finished the quiz. The number of questions you answered correctly were</p>
    <p>Click the button below to finish the quiz</p>
    {{correctAnswers}}
   
    <button @click="reset">Finish Quiz</button>
  </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      startQuiz: false,
      question: '',
      wrongAnswer: false,
      
      clickMe: false,
      notClick: false,
      qCount: 0,
      correctAnswers: `${this.qCount}/4`
    };
  },
  
   methods: {
    startTheQuiz() {
      let startQuiz = document.querySelector(".startQuiz");
      alert("Quiz Has Started");
      
      this.startQuiz = !this.startQuiz;
    },
    wrongAnswer() {
      return false;
    },
    reset() {
     let questionFormat = document.querySelector(".questionFormat")
     
     questionFormat.style.display = "none";
    }
  }
};
</script>

<style lang="scss">
body {
  background-color: lightgray;
}

#app {
  margin: 10px;
}

h2 {
  text-align: center;
  font-weight: bold;
  font-size: 1.5rem;
}

a,
button {
  color: #4fc08d;
}

button {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: block;
  margin: 1rem auto auto auto;
  padding: 0.5rem 1rem;
  background-color: lightgreen;
  color: white;
}

button:hover {
  cursor: pointer;
  background-color: green;
  color: white;
}
  
  .startQuizBtn {
    display: block;
  }
  
  .questionFormat {
    display: flex;
    justify-content: center;
    flex-direction: column;
    border: 1px solid black;
    padding: 2rem;
    animation: testAnimation;
    transition: 1s ease-in-out;
  }
  
  @keyframes testAnimation {
    from: {opacity: 0}
    to: {opacity: 1}
  }
  
  .testBtn {
    top: 40%;
  }
  
  .wrong {
color: red;
  }
  
 
</style>
