<!-- This app will be an interactive/well designed quiz app... User is asked a series of questions.. if answer correctly then move onto next page. Use alot of conditional rendering -->
<template>
  <div id="app">
    <h2>Quiz App</h2>
    
 <!-- Start Of Quiz (This starts the quiz off) Btn -->
    <button class="startQuizBtn" :class="{clicked: clickMe, notClicked: notClick}" @click="question = 'Q1'">Start Quiz</button>
 <!-- Use Conditional Class Binding -->
   <!-- Use V-for to display all wrong answers for each view -->
