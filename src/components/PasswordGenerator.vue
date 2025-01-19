<script setup>
  import { ref } from 'vue'

  const passwordLength = ref(12)
  const incUppercase = ref(true)
  const incNumbers = ref(true)
  const incSymbols = ref(true)
  const generatedPassword = ref('')

  // handler to generate the password
  const generatePassword = () => {
    const lowercaseChar = 'abcdefghijklmnopqrstuvwxyz'
    const uppercaseChar = incUppercase.value ? 'ABCDEFGHIJKLMNOPQRSTUVWXYZ' : ''
    const numberChars = incNumbers.value ? '1234567890' : ''
    const symbolChars = incSymbols.value ? '!@#$%^&*()-_=+[]{}|;:,.<>?/~' : ''
    const availableChars = lowercaseChar + uppercaseChar + numberChars + symbolChars

    // validate password length
    const validLength = Math.max(4, Math.min(passwordLength.value, 32))
    passwordLength.value = validLength

    // generate
    let password = ''
    for (let i = 0; i < passwordLength.value; i++) {
      const randomIndex = Math.floor(Math.random() * availableChars.length)
      password += availableChars[randomIndex]
    }

    generatedPassword.value = password
  }
</script>

<template>
  <form @submit.prevent="generatePassword" class="form-general">
    <h2>Password Generator</h2>

    <!-- length select -->
    <div class="form-input-item">
      <label for="passLength">Password length</label>
      <input type="number" id="passLength" v-model="passwordLength" min="4" max="32" />
    </div>

    <!-- options -->
    <div class="form-input-item">
      <div class="form-row">
        <input type="checkbox" id="incUpper" v-model="incUppercase" />
        <label for="incUpper">Include Uppercase</label>
      </div>
      <div class="form-row">
        <input type="checkbox" id="incNum" v-model="incNumbers" />
        <label for="incNum">Include Numbers</label>
      </div>
      <div class="form-row">
        <input type="checkbox" id="incSym" v-model="incSymbols" />
        <label for="incSym">Include Symbols</label>
      </div>
    </div>

    <!-- generate button -->
    <div class="m-t-1">
      <button type="button" @click="generatePassword" class="btn-main">Generate Password</button>
    </div>

    <!-- final output -->
    <div v-if="generatedPassword" class="form-output m-t-2">
      <p>{{ generatedPassword }}</p>
    </div>
  </form>
</template>

<style scoped>
  .form-general {
    padding: 2rem;
    background-color: #fff;
    border-radius: 4px;
    box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;
  }

  .form-input-item {
    .form-row {
      label {
        margin-bottom: 0;
      }
      input[type='checkbox'],
      input[type='radio'] {
        accent-color: #9f51cc;
        width: 20px;
        height: 20px;
        margin-bottom: 0;
      }
    }
  }

  .form-output {
    background-color: #9f51cc;
    padding: 1rem;
    border-radius: 4px;
    box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px;

    p {
      margin: 0;
      color: #fff;
      font-size: 1.35rem;
      text-align: center;
    }
  }
</style>
