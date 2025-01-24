<template>
  <div class="projects-container">
    <h2>Projects</h2>

    <!-- Project 1 -->
    <div class="project-row">
      <img src="@/assets/hackathon.png" alt="Project 1" class="project-image" />
      <div class="project-details">
        <h3>Glossi.fi Security Index</h3>
        <br>
        <div class="project-links">
          <a href="https://taikai.network/ethlisbon/hackathons/ethlisbon-2023/projects/clokm9k2306mtw001qg96v5l0/idea" target="_blank" rel="noopener noreferrer">View</a>
          <a href="https://github.com/djosey/glossifi-ethlisbon" target="_blank" rel="noopener noreferrer">GitHub</a>
        </div>
        <p>
          This was my teams submission to the <a href="https://ethlisbon.org" target="_blank" rel="noopener noreferrer" class="eth-link">ETH Lisbon</a>
          2023 hackathon. The project was a snapshot of Glossi.fi's main goal of using repuation to make
          smart contract interaction safer. I mainly worked on creating the frontend that works as a search engine to
          filter through smart contracts and then provide metadata on the searched address.
        </p>
      </div>
    </div>

    <!-- Project 2 -->
    <div class="project-row reverse">
      <div class="project-details">
        <h3>Mitch's Spots</h3>
       
        <div class="project-links">
          <a href="https://mitchwohead.com/spots" target="_blank" rel="noopener noreferrer">View</a>
          <a href="https://github.com/Mitch-Wohead/mitchs_spots" target="_blank" rel="noopener noreferrer">GitHub</a>
        </div>
        <p>
         A passion project made with Mapbox & React.js, this is a map and chart of every bar and resturant I have been to in Dallas. I use this site to send to out of town friends who are visting.
        </p>
      </div>
      <img src="@/assets/Spots.png" alt="Project 2" class="project-image" />
    </div>

    <!-- Project 3 -->
    <div class="project-row">
      <img src="@/assets/Apollo.png" alt="Project 3" class="project-image" />
      <div class="project-details">
        <h3>Apollo Graph QL Server & Telegram Bot</h3>
        <div class="project-links">
          <a href="https://studio.apollographql.com/sandbox/explorer" target="_blank" rel="noopener noreferrer">View</a>
          
        </div>
        <p>
          Made in Python, this graph QL server takes mongoDB data held on a cloud server and queries it into a simple format for API calls. This server is also set up to send a telegram notification to <a href="https://t.me/glossifi" target="_blank" rel="noopener noreferrer">t.me/glossifi</a> via a telegram bot that I also created in Python anytime new data is submitted into the mongoDB backend.
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.eth-link {
  color: black; /* Makes the link text black */
  text-decoration: none; /* Removes underline */
  font-weight: bold; /* Optional: Make it bold */
  transition: color 0.3s ease; /* Smooth color transition on hover */
}

.eth-link:hover {
  color: #555; /* Subtle color change on hover */
}
/* Container styles */
.projects-container {
  padding: 2rem;
}

h2 {
  font-size: 2.5rem; /* Make the text larger */
  font-weight: 800; /* Bold and prominent */
  color: #333; /* Dark gray for a clean look */
  margin-bottom: 1.5rem; /* Increase spacing below */
  text-transform: uppercase; /* Optional: Make the text all caps */
  letter-spacing: 0.05rem; /* Add spacing between letters */
  text-align: Center;

}

h3 {
  text-align: center;
  margin-bottom: 2rem;
}

/* Project row styles */
.project-row {
  display: flex;
  align-items: center;
  margin-bottom: 2rem;
  gap: 1rem;
}

/* Reverse row for alternating layout */
.project-row.reverse {
  display: flex;
  align-items: center;
  margin-bottom: 2rem;
  gap: 1rem;
}

/* Image styles */
.project-image {
  width: 40%;
  height: auto;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

/* Details styles */
.project-details {
  width: 50%;
  text-align: left;
}

.project-details h3 {
  margin-bottom: 0.5rem;
}

.project-details p {
  line-height: 1.6;
  color: #555;


}


.project-links {
  display: flex;
  justify-content: center; /* Centers the links horizontally */
  gap: 1rem; /* Space between the links */
  margin: 0.5rem 0 1rem 0; /* Adds spacing above and below the links */
}

.project-links a {
  text-decoration: none;
  color: #007bff; /* Link color */
  font-weight: bold;
  border: 1px solid #007bff;
  padding: 0.5rem 1rem;
  border-radius: 5px;
  transition: background-color 0.3s, color 0.3s;
}

.project-links a:hover {
  background-color: #007bff;
  color: #fff; /* White text on hover */
}

@media (max-width: 768px) {
  /* Center the container */
  .projects-container {
    padding: 1rem;
    text-align: center;
  }

  /* Project row layout for mobile */
  .project-row {
    flex-direction: column; /* Stack all content vertically */
    align-items: center; /* Center all content */
    text-align: center; /* Center text for project details */
  }

  /* Ensure links are on top */
  .project-links {
    order: 1; /* Position project-links first */
    justify-content: center;
    margin-bottom: 1rem; /* Add spacing below links */
  }

  /* Text comes next */
  .project-details {
    order: 2; /* Position project-details second */
    width: 90%; /* Full width for better readability */
    text-align: center; /* Center the text */
  }

  /* Image comes last */
  .project-image {
    order: 3; /* Position image last */
    width: 80%; /* Reduce image size for smaller screens */
    height: auto; /* Maintain aspect ratio */
    margin-top: 1rem; /* Add spacing above the image */
  }
}
</style>