<template>
  <div class="country-page">
    <h2 class="country-title">{{ country.name }} - Medal Details</h2>
    
    <!-- Country Info Section -->
    <div class="section">
      <h3 class="section-title">Country Info</h3>
      <div class="country-info">
        <p><strong>Gold Medals:</strong> {{ country.gold }}</p >
        <p><strong>Silver Medals:</strong> {{ country.silver }}</p >
        <p><strong>Bronze Medals:</strong> {{ country.bronze }}</p >
      </div>
    </div>
    
    <!-- Sports Section -->
    <div class="section">
      <h3 class="section-title">Sports</h3>
      <ul class="sports-list">
        <li v-for="sport in country.sports" :key="sport.id" class="sport-item">
          <span class="sport-name">{{ sport.name }}</span> 
          <span class="sport-medals">Medals: {{ sport.medals }}</span>
        </li>
      </ul>
    </div>

    <!-- Comment Section -->
    <div class="comments-section">
      <h3 class="section-title">Comments</h3>
      <comment-section :comments="country.comments" />
    </div>
  </div>
</template>

<script>
import CommentSection from '../components/CommentSection.vue';

export default {
  components: {
    CommentSection,
  },
  data() {
    return {
      country: {
        id: this.$route.params.id,
        name: 'Country 1',
        gold: 5,
        silver: 3,
        bronze: 2,
        sports: [
          { id: 1, name: 'Football', medals: 2 },
          { id: 2, name: 'Swimming', medals: 3 },
        ],
        comments: [
          { id: 1, username: 'User1', avatar: 'https://randomuser.me/api/portraits/men/1.jpg', text: 'Great performance!' },
          { id: 2, username: 'User2', avatar: 'https://randomuser.me/api/portraits/women/2.jpg', text: 'Well done!' },
        ],
      },
    };
  },
};
</script>

<style scoped>
/* General Styles */
.country-page {
  font-family: 'Arial', sans-serif;
  max-width: 900px;
  margin: 20px auto;
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

.country-tit
  
