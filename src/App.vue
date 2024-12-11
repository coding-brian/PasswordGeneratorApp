<script setup>
import { computed, reactive, ref } from 'vue'

const password = ref('')
const conditionType = {
  uppercase: 0,
  lowercase: 1,
  number: 2,
  symbol: 3,
}
const conditions = [
  {
    type: conditionType.uppercase,
    name: 'Include Uppercase Letters',
    value: conditionType.uppercase,
  },
  {
    type: conditionType.lowercase,
    name: 'Include Lowercase Letters',
    value: conditionType.lowercase,
  },
  {
    type: conditionType.number,
    name: 'Include Numbers',
    value: conditionType.number,
  },
  {
    type: conditionType.symbol,
    name: 'Include Symbols',
    value: conditionType.symbol,
  },
]
const selectedConditions = ref([])
const characterLength = reactive({
  max: 20,
  min: 0,
  value: 0,
})
const range = ref(null)

const strengthFigure = computed(() => {
  if (selectedConditions.value.length <= 0) return null
  const result = {
    name: '',
    total: 4,
    count: selectedConditions.value.length,
    remaining: 0,
    class: {
      rectangle: true,
    },
  }

  result.remaining = result.total - result.count
  switch (result.count) {
    case 1:
      result.class['too-week'] = true
      result.name = 'TOO WEAK!'
      break
    case 2:
      result.class['week'] = true
      result.name = 'WEAK'
      break
    case 3:
      result.class['medium'] = true
      result.name = 'MEDIUM'
      break
    case 4:
      result.class['strong'] = true
      result.name = 'STRONG'
      break
  }

  return result
})
const rangeHandler = (el) => {
  const percentage = (characterLength.value / characterLength.max) * 100
  if (percentage > 0) {
    el.target.style.background = `linear-gradient(to right, var(--neon-green) ${percentage}%,var(--very-dark-grey) 0%)`
  }
}
</script>

<template>
  <main>
    <span class="title heading-m">Password Generator</span>
    <div class="generator">
      <div class="password-container">
        <span class="password heading-l">{{ password }}</span>
        <img src="./assets/icon-copy.svg" alt="" class="copy-img" />
      </div>
      <div class="condition-container">
        <div class="character-length-container">
          <div class="character-length">
            <span class="title heading-m">Character Length</span>
            <span class="number heading-l">{{ characterLength.value }}</span>
          </div>
          <input
            type="range"
            ref="range"
            name=""
            id=""
            :min="characterLength.min"
            :max="characterLength.max"
            v-model.number="characterLength.value"
            @input="rangeHandler"
          />
        </div>
        <div class="condition">
          <div class="checkbox-container" v-for="condition in conditions" :key="condition.type">
            <input type="checkbox" :value="condition.type" v-model="selectedConditions" /><span
              class="heading-m"
              >{{ condition.name }}</span
            >
          </div>
        </div>
        <div class="strength-container">
          <span class="title body">STRENGTH</span>
          <div class="strength-figure" v-if="strengthFigure">
            <span class="strength-figure-title heading-m">{{ strengthFigure.name }}</span>
            <div class="figure">
              <div
                v-for="(count, index) in strengthFigure.count"
                :class="strengthFigure.class"
                :key="index"
              ></div>
              <div
                v-for="(count, index) in strengthFigure.remaining"
                class="rectangle"
                :key="index"
              ></div>
            </div>
          </div>
        </div>
        <button class="button">
          <span class="text heading-m">GENERATE</span>
          <div class="arrow-right"></div>
        </button>
      </div>
    </div>
  </main>
</template>

<style scoped></style>
