<script setup>
import { defineProps, defineEmits, ref } from 'vue'
import * as yup from 'yup';

defineProps({
  placeholder: {
    type: String,
    default: 'Email Adress',
  },
  buttonAriaLabel: {
    type: String,
    default: 'submit email',
  },
  buttonIconSrc: {
    type: String,
    default: '/icon-arrow.svg',
  }
})

const email = ref('')
const iconError = ref(false)
const errorMessage = ref('');

const emit = defineEmits(['submit'])

const emailValidationRule = yup.string().email('Invalid email address');

const validateEmail = async () => {
  try {
    await emailValidationRule.validate(email.value)
    errorMessage.value = '';
  } catch (err) {
    errorMessage.value = err.message || 'Invalid input';
  }
};

const handleSubmit = async () => {
  try {
    await validateEmail(); 
    if (!email.value) {
      errorMessage.value = 'Email must be provided';
    }
    if (!errorMessage.value) {
      emit('submit', email.value);
      email.value = '';
    }
  } catch (err) {
    errorMessage.value = err.message || 'Validation failed'; // Set error message if validation fails
  }
};
</script>

<template>
  <div id="email-wrapper">
    <div id="input-wrapper">
      <input type="email" name="email" v-model="email" :placeholder="placeholder" @blur="validateEmail" />
      <button type="button" :aria-label="buttonAriaLabel" @click="handleSubmit">
        <img
          v-if="buttonIconSrc && !iconError"
          :src="buttonIconSrc"
          alt="Button Icon"
          width="10"
          height="18"
          @error="iconError = true"
        />
        <span v-else>Send</span>
      </button>
    </div>
    <p v-if="errorMessage" class="error">{{ errorMessage }}</p>
  </div>
</template>

<style scoped>
#input-wrapper {
  position: relative;
  width: 100%;
  margin-top: 1rem;
}

#email-wrapper {
  position: relative;
  width: 100%;
  margin-top: 1rem;
}

.error {
  margin: 16px 0px 0px 16px;
}

/* Style the input field */
#email-wrapper input {
  border: solid 1px var(--gray-soft);
  border-radius: 2rem;
  padding: 1rem 1.5rem;
  height: 48px;
  width: 100%;
  font-size: 16px;
  outline: none;
  box-sizing: border-box;
}

input::placeholder {
  color: var(--gray-soft);
  font-size: 14px;
}

#email-wrapper button {
  position: absolute;
  top: 50%;
  right: 0;
  transform: translateY(-50%);
  background: var(--gradient-soft-red);
  color: white;
  border: none;
  border-radius: 2rem;
  height: 48px;
  width: 64px;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  transition:
    opacity 0.3s ease,
    box-shadow 0.3s ease;
  opacity: 1;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
}

/* Button hover effect */
#email-wrapper button:hover {
  opacity: 0.8;
  box-shadow: 0 6px 10px rgba(0, 0, 0, 0.3);
}

/* Input focus styling */
#email-wrapper input:focus {
  border: solid 2px var(--primary-soft-red);
}

#email-wrapper button:active {
  transform: translateY(-50%) scale(0.98); /* Slightly shrink the button */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2); /* Reduce shadow */
  opacity: 0.7; /* Slightly reduce opacity */
}

@media (min-width: 1024px) {
  #email-wrapper button {
    width: 88px;
    font-size: 16px;
  }
}
</style>
