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
