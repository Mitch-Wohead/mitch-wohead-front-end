<template>
  <div class="about-container">
    <!-- Header -->
    <h2>About</h2>

    <div class="about-content">
      <!-- Paragraphs on the left -->
      <div class="about-text">
        <p>
          I'm a self-taught developer from Dallas, Texas who started by learning <span class="highlight">Javascript</span> through making <span class="highlight">Vue.js</span> apps (like this one). Since then I have made full-stack web and IOS projects with <span class="highlight">  React.js,
          React-Native, Python, GraphQL, Solidity, and Go-Lang. </span>
        </p>
        <p>
  I graduated from the <a href="https://www.youtube.com/watch?v=-BQe5wv5E3s" target="_blank" rel="noopener noreferrer" class="university-link">University of Kansas</a> in 2022 with a double major in Finance and Marketing and since then I have been working on a variety of exciting projects for NSF grant-funded Glossi.fi.
  I'm a web3 enthusiast and have had the opportunity to attend and participate in multiple web3 conferences and hackathons.
</p>
        <p>
          In my free time, I like to run, travel, fish, and getting overly invested in my sports teams.
        </p>
      </div>

      <!-- Picture carousel on the right -->
      <div class="carousel">
        <button class="arrow left-arrow" @click="prevImage">❮</button>
        <img :src="currentImage" :alt="'Picture ' + (currentIndex + 1)" class="carousel-image" />
        <button class="arrow right-arrow" @click="nextImage">❯</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';

// Array of image paths
const images = [
new URL('@/assets/Lisbon.png', import.meta.url).href,
  new URL('@/assets/Denver.png', import.meta.url).href,
  new URL('@/assets/Kansas.png', import.meta.url).href,
  
  new URL('@/assets/Maine.png', import.meta.url).href,
  new URL('@/assets/Montana.png', import.meta.url).href,
  new URL('@/assets/Plano.png', import.meta.url).href,
];

// Reactive state for the current image index
const currentIndex = ref(0);

// Computed property to get the current image
const currentImage = computed(() => images[currentIndex.value]);

// Methods to navigate the carousel
const nextImage = () => {
  currentIndex.value = (currentIndex.value + 1) % images.length;
};

const prevImage = () => {
  currentIndex.value = (currentIndex.value - 1 + images.length) % images.length;
};
</script>

<style scoped>
/* Container styles */
.about-container {
  display: flex;
  flex-direction: column;
  padding: 2rem;
  height: 80%;
}

/* Header styles */
h2 {
  font-size: 2.5rem; /* Make the text larger */
  font-weight: 800; /* Bold and prominent */
  color: #333; /* Dark gray for a clean look */
  margin-bottom: 1.5rem; /* Increase spacing below */
  text-transform: uppercase; /* Optional: Make the text all caps */
  letter-spacing: 0.05rem; /* Add spacing between letters */
 

}

/* Content layout */
.about-content {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 2rem;
}

/* Text section styles */
.about-text {
  flex: 1;
  max-width: 45%; /* Keeps text on the left side */
  text-align: left;
  font-size: 1rem;
  line-height: 1.6;
}

/* Carousel styles */
.carousel {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  background-color: #377b5d;
}

.carousel-image {
  height: 50vh; /* 50% of the viewport height */
  width: auto; /* Automatically adjusts the width to maintain aspect ratio */
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(145, 41, 41, 0.1);
  
}
.arrow {
  position: absolute;
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  border: none;
  font-size: 2rem;
  width: 50px;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  user-select: none;
  border-radius: 10px;
  transition: background-color 0.3s;
  z-index: 10; 
}

.arrow:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

.left-arrow {
  left: 0
}

.right-arrow {
  right: 0;
}

.highlight {
  color: #42b983; /* The green color you're using */
  font-weight: bold; 
  
}
.university-link {
  font-weight: bold; /* Makes the text bold */
  color: black; /* Sets the text color to black */
  text-decoration: none; /* Removes the underline from the link */
  transition: color 0.3s ease; /* Adds a smooth hover effect */
}

.university-link:hover {
  color: #555; /* Change color on hover for better interactivity */
}


@media (max-width: 768px) {
  /* About content layout for mobile */
  h2{
    text-align: center;
  }
  .about-content {
    flex-direction: column; /* Stack the text and carousel vertically */
    align-items: center; /* Center-align the content */
    text-align: center; /* Center-align the text */
  }

  /* Text section adjustments */
  .about-text {
    max-width: 90%; /* Allow more space for text on smaller screens */
    margin-bottom: 2rem; /* Add spacing below the text */
  }

  /* Carousel adjustments */
  .carousel {
    width: 100%; /* Make the carousel fill the width */
    padding: 1rem; /* Add padding for spacing */
  }

  .carousel-image {
    width: 80%; /* Scale the image down for smaller screens */
    height: auto; /* Maintain the aspect ratio */
  }
}
</style>