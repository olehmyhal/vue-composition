<template>
  <div>
    <h2>My Course Goal</h2>
    <p>{{ mainGoal }}</p>
    <!-- Task 1: Output your main course goal with help of the composition API -->
    <!-- Don't hardcode it into the template, instead hardcode it into the JS code -->
    <h3>OUTPUT COURSE GOAL</h3>
    <!-- Task 2: Toggle (show/ hide) the goal with help of the button  -->
    <button @click="toggleText">{{ isShownText ? 'Show' : 'Hide' }}</button>
    <!-- Task 3: Manage data in three ways -->
    <!-- => Separate refs -->
    <!-- => Ref Object -->
    <!-- => Reactive Object -->
    <!-- Task 4: Also solve the assignment with the Options API -->
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup(){
    const mainGoal = ref('To become a google software developer')
    const isShownText = ref(true)

    const toggleText = () => isShownText.value = !isShownText.value

    return { mainGoal, toggleText, isShownText }
  }
}
</script>

<style>
html {
  font-family: sans-serif;
}
body {
  margin: 3rem;
  text-align: center;
}
</style>