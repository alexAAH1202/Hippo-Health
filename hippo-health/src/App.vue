<template>
  <div class="app">
    <header>
      <nav>
        <img :src="logo" alt="Hippo Health Logo" class="logo">
        <ul>
          <li><a href="#about">About</a></li>
          <li><a href="#features">Features</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </header>

    <main>
      <section id="hero">
        <h1>Streamline Your NDIS Workflow with Hippo Health</h1>
        <p>Enjoy more work-life balance and focus on what matters most: your clients.</p>
        <div class="coming-soon">Coming Soon</div>
      </section>

      <section id="about">
        <h2>About Hippo Health</h2>
        <p>Hippo Health combines workflow automation with AI technologies to revolutionize NDIS administrative tasks.</p>
      </section>

      <section id="features">
        <h2>Key Features</h2>
        <div class="feature" v-for="feature in features" :key="feature.title">
          <img :src="feature.image" :alt="feature.title" class="hippo-agent">
          <h3>{{ feature.title }}</h3>
          <p>{{ feature.description }}</p>
        </div>
      </section>

      <section id="contact">
        <h2>Stay Updated</h2>
        <p>Want to know when we launch? Leave your email below!</p>
        <form @submit.prevent="submitForm">
          <input v-model="email" type="email" placeholder="Enter your email" required>
          <button type="submit">Notify Me</button>
        </form>
      </section>
    </main>

    <footer>
      <p>&copy; {{ new Date().getFullYear() }} Hippo Health. All rights reserved.</p>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import logo from './assets/1.png'
import hippo1 from './assets/2.png'
import hippo2 from './assets/3.png'

const email = ref('')

const features = [
  {
    title: 'Streamlined Administration',
    description: 'Automate routine tasks and paperwork to free up your time.',
    image: hippo1
  },
  {
    title: 'AI-Powered Reporting',
    description: 'Generate comprehensive reports from existing notes with our advanced AI.',
    image: hippo2
  },
  {
    title: 'Dynamic Intake Forms',
    description: 'Create adaptive forms that adjust to each patient\'s unique needs.',
    image: hippo3
  }
]

const submitForm = () => {
  // Here you would typically send the email to your backend
  console.log('Form submitted with email:', email.value)
  email.value = '' // Clear the input after submission
}
</script>

<style scoped>
/* Add your CSS styles here */
:root {
  --primary-blue: #3498db;
  --secondary-blue: #2980b9;
  --primary-purple: #9b59b6;
  --secondary-purple: #8e44ad;
  --light-gray: #ecf0f1;
  --dark-gray: #34495e;
}

.app {
  font-family: Arial, sans-serif;
  line-height: 1.6;
  color: var(--dark-gray);
}

header {
  background-color: var(--primary-blue);
  padding: 1rem;
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  height: 50px;
}

nav ul {
  display: flex;
  list-style-type: none;
}

nav ul li {
  margin-left: 1rem;
}

nav ul li a {
  color: white;
  text-decoration: none;
}

main {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}

#hero {
  text-align: center;
  background-color: var(--light-gray);
  padding: 4rem 2rem;
  border-radius: 10px;
}

h1 {
  color: var(--primary-purple);
}

.coming-soon {
  display: inline-block;
  background-color: var(--secondary-purple);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 5px;
  margin-top: 1rem;
}

#features {
  display: flex;
  justify-content: space-between;
  margin-top: 2rem;
}

.feature {
  flex-basis: 30%;
  text-align: center;
  padding: 1rem;
  background-color: var(--light-gray);
  border-radius: 10px;
}

.hippo-agent {
  width: 100px;
  height: 100px;
  object-fit: contain;
}

form {
  display: flex;
  margin-top: 1rem;
}

input[type="email"] {
  flex-grow: 1;
  padding: 0.5rem;
  border: 1px solid var(--primary-blue);
  border-radius: 5px 0 0 5px;
}

button {
  background-color: var(--primary-blue);
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  border-radius: 0 5px 5px 0;
}

button:hover {
  background-color: var(--secondary-blue);
}

footer {
  background-color: var(--primary-purple);
  color: white;
  text-align: center;
  padding: 1rem;
  margin-top: 2rem;
}
</style>