<script setup>
import Home from './components/Home.vue'
import About from './components/About.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'

const scrollTo = (sectionId) => {
  const section = document.getElementById(sectionId);
  if (section) {
    section.scrollIntoView({ behavior: 'smooth', block: 'start' });
  }
};
</script>

<template>
  <header>
    <div class="header-container">
      <!-- Home link on the left -->
      <a href="#home" class="logo" @click.prevent="scrollTo('home')">
  <img src="@/assets/mw.png" alt="Logo" class="logo-image" />
</a>

      <!-- Navigation in the center -->
      <nav>
        <a href="#about" @click.prevent="scrollTo('about')">About</a>
        <a href="#projects" @click.prevent="scrollTo('projects')">Projects</a>
        <a href="#contact" @click.prevent="scrollTo('contact')">Contact</a>
      </nav>
    </div>
  </header>

  <main>
    <section id="home">
      <Home />
    </section>
    <section id="about">
      <About />
    </section>
    <section id="projects">
      <Projects />
    </section>
    <section id="contact">
      <Contact />
    </section>
  </main>
</template>

<style scoped>
.logo-image {
  height: auto; /* Keep the original height */
  width: auto; /* Keep the original width */
  max-height: 50px; /* Limit the maximum height for consistency */
  max-width: 50px; /* Limit the maximum width */
  border-radius: 20%; /* Make it circular */
   /* Optional green border */
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2); /* Subtle shadow for style */
  transition: transform 0.3s ease-in-out; /* Smooth hover animation */
}

.logo-image:hover {
  transform: scale(1.1); /* Slight zoom effect on hover */
}
/* Header styles */
header {
  position: sticky;
  top: 0;
  background: white;
  z-index: 1000;
  border-bottom: 1px solid #ddd;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  padding: 1rem 2rem;
}

/* Header container layout */
.header-container {
  display: flex;
  justify-content: space-between; /* Space between Home and the rest */
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
}

/* Center navigation menu */
nav {
  display: flex;
  justify-content: center;
  gap: 2rem; /* Space between links */
  flex: 1.8; /* Ensures the nav fills space and centers itself */
}

/* Logo (Home link) styles */
.logo {
  font-size: 1.5rem;
  font-weight: bold;
  color: #42b983;
  text-decoration: none;
  margin-right: auto; /* Pushes navigation to the center */
}

.logo:hover {
  color: #2c7a7b;
}

/* Navigation styles */
nav a {
  font-size: 1.5rem;
  font-weight: bold;
  color: #42b983;
  text-decoration: none;
  transition: color 0.3s;
}

nav a:hover {
  color: #16432f;
  transform: scale(1.1);
}


/* Main content styles */
main {
  margin-top: 0rem; /* Space between header and main content */
}

section {
  padding: 4rem 1rem;
  border-bottom: 1px solid #eee;
}

section:last-child {
  border-bottom: none;
}

#home {
  background: #f9f9f9;
}

#about {
  background: #ffffff;
}

#projects {
  background: #f4f4f4;
}

#contact {
  background: #f9f9f9;
}

@media (max-width: 768px) {
  /* Logo adjustments */
  .logo-image {
    max-height: 30px; /* Reduce logo size */
    max-width: 30px;
  }

  /* Header padding */
  header {
    padding: 0.5rem 1rem; /* Reduce padding for smaller screens */
  }

  /* Navigation menu adjustments */
  nav {
    gap: 1rem; /* Reduce spacing between navigation links */
  }

  nav a {
    font-size: 1rem; /* Smaller font size for links */
  }
}



</style>