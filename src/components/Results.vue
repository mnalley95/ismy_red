<template>
  <div class="results-container">
    <div class="prank-gradient">
      <div v-if="loading" class="spinner-container">
        <div class="spinner"></div>
        <p>Calculating results...</p>
      </div>
      <div v-else class="prank-message">
        <h1>I have no idea, shouldn't you be reading the SDD? 🤓</h1>
        <button @click="$emit('reset')" class="reset-button">Try Again</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ResultsView',
  emits: ['reset'],
  data() {
    return {
      loading: true
    }
  },
  mounted() {
    setTimeout(() => {
      this.loading = false
    }, 3000)
  }
}
</script>

<style scoped>
.results-container {
  width: 100%;
  height: 100%;
}

.prank-gradient {
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, #ff0000, #ff6b6b);
  display: flex;
  align-items: center;
  justify-content: center;
}

.prank-message {
  text-align: center;
  color: white;
  padding: 2rem;
}

.prank-message h1 {
  font-size: 3rem;
  margin-bottom: 2rem;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
}

.reset-button {
  background: white;
  color: #ff0000;
  border: none;
  padding: 1rem 2rem;
  font-size: 1.2rem;
  border-radius: 8px;
  cursor: pointer;
  transition: transform 0.2s;
}

.reset-button:hover {
  transform: scale(1.05);
}

.spinner-container {
  text-align: center;
  color: white;
}

.spinner-container p {
  margin-top: 1rem;
  font-size: 1.2rem;
}

.spinner {
  width: 50px;
  height: 50px;
  border: 5px solid rgba(255, 255, 255, 0.3);
  border-radius: 50%;
  border-top-color: white;
  animation: spin 1s ease-in-out infinite;
  margin: 0 auto;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}
</style>
