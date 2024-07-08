<template>
    <div>
      <div class="feedback-form" v-if="showForm">
        <h2>How would you rate your satisfaction with our product?</h2>
        <div class="stars">
          <span v-for="star in 5" :key="star" class="star" :class="{ filled: star <= rating }" @click="submitFeedback(star)">
            &#9733;
            <span class="star-number">{{ star }}</span>
          </span>
        </div>
        <div class="rating-labels">
          <span class="left-label">Very dissatisfied</span>
          <span class="right-label">Very satisfied</span>
        </div>
        <p v-if="message">{{ message }}</p>
      </div>
      <p v-if="!showForm">{{ message }}</p>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
  data() {
    return {
      rating: 0,
      message: '',
      showForm: true
    };
  },
  methods: {
    async submitFeedback(star) {
      this.rating = star;
      console.log('Submitting feedback with rating:', this.rating);  // Add this line
      try {
        const response = await axios.post('http://127.0.0.1:8000/feedback/', {
          rating: this.rating
        });
        console.log('Response:', response.data);  // Add this line
        this.message = 'Feedback submitted successfully!';
        this.showForm = false;
      } catch (error) {
        console.error('Error submitting feedback:', error);  // Add this line
        this.message = 'Failed to submit feedback. Please try again.';
        this.showForm = true;
      }
    }
  }
  };
  </script>
  
  <style scoped>
  .feedback-form {
    max-width: 400px;
    margin: auto;
    padding: 1em;
    border: 1px solid #ccc;
    border-radius: 4px;
    background-color: white;
    color: black;
  }
  
  .feedback-form h2 {
    text-align: left;
    margin-bottom: 1em;
    color: black;
  }
  
  .stars {
    display: flex;
    justify-content: center;
    margin-bottom: 1em;
  }
  
  .star {
    font-size: 3em;
    cursor: pointer;
    color: #ccc;
    margin: 0 10px;
    position: relative;
  }
  
  .star.filled {
    color: #ffd700;
  }
  
  .star-number {
    position: absolute;
    top: 60px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 16px;
    color: black;
  }
  
  .rating-labels {
    display: flex;
    justify-content: space-between;
    margin-bottom: 1em;
    font-size: 12px;
    width: 100%;
    color: black;
  }
  
  .feedback-form p {
    text-align: center;
    font-weight: bold;
    margin-top: 1em;
    color: black;
  }
  </style>
  