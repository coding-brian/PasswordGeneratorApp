<script setup></script>

<template>
  <main>
    <span class="title heading-m">Password Generator</span>
    <div class="generator">
      <div class="password-container">
        <span class="password heading-l">456</span>
        <img src="./assets/icon-copy.svg" alt="" />
      </div>
      <div class="condition-container">
        <div class="character-length-container">
          <div class="character-length">
            <span class="title heading-m">Character Length</span>
            <span class="number heading-l">10</span>
          </div>
          <input type="range" name="" id="" />
        </div>
        <div class="condition">
          <div><input type="checkbox" name="" id="" /></div>
          <div><input type="checkbox" name="" id="" /></div>
          <div><input type="checkbox" name="" id="" /></div>
          <div><input type="checkbox" name="" id="" /></div>
        </div>
        <div class="strength-container"></div>
        <button class="button">
          <div>
            <span class="text heading-m">GENERATE</span>
            <img src="./assets/icon-arrow-right.svg" alt="" />
          </div>
        </button>
      </div>
    </div>
  </main>
</template>

<style scoped></style>
