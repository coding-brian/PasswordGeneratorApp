<script setup></script>

<template>
  <main>
    <span class="title heading-m">Password Generator</span>
    <div class="generator">
      <div class="password-container">
        <span class="password heading-l">456</span>
        <img src="./assets/icon-copy.svg" alt="" class="copy-img" />
      </div>
      <div class="condition-container">
        <div class="character-length-container">
          <div class="character-length">
            <span class="title heading-m">Character Length</span>
            <span class="number heading-l">10</span>
          </div>
          <input type="range" name="" id="" min="0" max="20" value="10" />
        </div>
        <div class="condition">
          <div class="checkbox-container">
            <input type="checkbox" class="test" name="" id="" /><span class="heading-m"
              >Include Uppercase Letters</span
            >
          </div>
          <div class="checkbox-container">
            <input type="checkbox" class="checkbox" name="" id="" /><span class="heading-m"
              >Include Lowercase Letters</span
            >
          </div>
          <div class="checkbox-container">
            <input type="checkbox" class="checkbox" name="" id="" /><span class="heading-m"
              >Include Numbers</span
            >
          </div>
          <div class="checkbox-container">
            <input type="checkbox" class="checkbox" name="" id="" /><span class="heading-m"
              >Include Symbols</span
            >
          </div>
        </div>
        <div class="strength-container">
          <span class="title body">STRENGTH</span>
          <div class="strength-figure">
            <span class="strength-figure-title heading-m">MEDIUM</span>
            <div class="figure">
              <div class="rectangle too-week"></div>
              <div class="rectangle"></div>
              <div class="rectangle"></div>
              <div class="rectangle"></div>
            </div>
          </div>
        </div>
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
