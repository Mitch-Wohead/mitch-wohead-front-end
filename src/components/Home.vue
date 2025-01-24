<template>
    <div class="home-container">
      <!-- Logo in the middle -->
      <img src="@/assets/Maine2.png" alt="Logo" class="home-logo" />
  
      <!-- Welcome message -->
      <h1 class="home-title">
  Hi, my name is <span class="highlight">Mitch.</span>
</h1>
      <p class="home-subtitle">I'm a developer and creator</p>
    </div>
  </template>
  
  <style scoped>
  /* Center the container */
  /* Style the logo as a profile picture */
.home-logo {
  width: 300px; /* Adjust size as needed */
  height: auto;
  margin-bottom: 1.5rem;
  border-radius: 50%; /* Makes the image circular */
  border: 3px solid black; /* Adds a black border */
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3); /* Adds a subtle shadow for a polished look */
}
  .home-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh; /* Full viewport height */
    text-align: center;
  }
  
  /* Style the logo */

  /* Style the text */
  .home-title {
    font-size: 2rem; /* Adjust for big font */
    font-weight: 800; /* ExtraBold font */
    font-family: 'Montserrat', sans-serif; /* Use Montserrat */
  }
  .home-subtitle {
  font-size: 1.2rem; /* Smaller font size */
  color: #555; /* Subtle color */
  font-weight: 400; /* Normal weight */
  font-family: 'Montserrat', sans-serif; /* Use Montserrat */
}

.highlight {
  color: #42b983; /* The green color you're using */
}
  </style>