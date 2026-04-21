<template>
  <div class="page fade-in">
    <h1>Creative</h1>

    <!-- Hobbies Section -->
    <section class="hobbies">
      <center>
      <h2>My Hobbies 🎨</h2>
      <p>Click on a hobby to see a little fun fact!</p>
      </center>
      <div class="hobby-cards">
        <div
          v-for="(hobby, index) in hobbies"
          :key="index"
          class="hobby-card"
          @click="toggleHobby(index)"
          :class="{ active: hobby.active }"
        >
          <h3>{{ hobby.name }}</h3>
          <p v-if="hobby.active">{{ hobby.description }}</p>
        </div>
      </div>
    </section>

    <!-- Resume Section -->
    <section class="resume">
      <center><h2>Resume 📄</h2></center>
      <div class="resume-content">
        <h3>{{ resume.name }}</h3>
        <p><strong>Course:</strong> {{ resume.course }}</p>
        <p><strong>School:</strong> {{ resume.school }}</p>
        <p><strong>Email:</strong> {{ resume.email }}</p>
        <p><strong>Skills:</strong> {{ resume.skills.join(', ') }}</p>

        <h4>Experience:</h4>
        <ul>
          <li v-for="(exp, i) in resume.experience" :key="i">{{ exp }}</li>
        </ul>

        <h4>Projects:</h4>
        <ul>
          <li v-for="(proj, i) in resume.projects" :key="i">
            <a :href="proj.link" target="_blank" rel="noopener noreferrer">{{ proj.name }}</a>
          </li>
        </ul>
      </div>
    </section>

    <!-- Business-style Calculator -->
    <section class="calculator">
      <h2>Calculator (mini-app) 🧮</h2>
      <div class="calculator-container">
        <input type="text" :value="display" readonly />

        <div class="buttons">
          <button @click="clearAll">C</button>
          <button @click="deleteLast">DEL</button>
          <button @click="appendOperator('/')">/</button>
          <button @click="appendOperator('*')">*</button>

          <button v-for="n in [7,8,9]" :key="n" @click="appendNumber(n)">{{ n }}</button>
          <button @click="appendOperator('-')">-</button>

          <button v-for="n in [4,5,6]" :key="n" @click="appendNumber(n)">{{ n }}</button>
          <button @click="appendOperator('+')">+</button>

          <button v-for="n in [1,2,3]" :key="n" @click="appendNumber(n)">{{ n }}</button>
          <button @click="calculate" class="equals">=</button>

          <button @click="appendNumber(0)" class="zero">0</button>
          <button @click="appendDot()">.</button>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "Creatives",
  data() {
    return {
      // Hobbies
      hobbies: [
        { name: "Digital Art", description: "I create digital illustrations and designs using Photoshop and Illustrator.", active: false },
        { name: "Video Editing", description: "Editing videos for short films, YouTube, and presentations with Premiere Pro, Filmora, and also CapCut.", active: false },
        { name: "Graphic Design", description: "Designing posters, flyers, and social media content. Canva and Photoshop are my go-to tools. And in terms of Publishing/Publication, I use InDesign", active: false },
        { name: "Gaming", description: "I like MMORPG games especially majority of Hoyoverse games like Genshin Impact, Honkai Star Rail, and Zenless Zone Zero.", active: false },
        { name: "Audio Editing", description: "Aside from both picture and video editing, I also edit audio clips like enhancing them etc..", active: false },
      ],
      // Resume
      resume: {
        name: "Elton Jhon M. Pabuayon",
        course: "BS Computer Engineering",
        school: "Polytechnic University of the Philippines",
        email: "eltonjhonmartinez@gmail.com",
        skills: ["Programming (HTML, CSS, C++, Python, Javascript)", "Photo Editing and Layout Design (Adobe Photoshop, Illustrator, InDesign, and Canva)", "Video Editing (Adobe Premiere Pro)", "Audio Editing (Adobe Audition)"],
        experience: [
          "Graphic Designer and Layout Artist at own Family Business (2016–Present)",
          "Digital Marketing Intern at Zoomanity Group (2023)",
          "Administrative Aide Intern at Department of Environment and Natural Resources (2019)",
        ],
        projects: [
          { name: "RaketPH", link: "https://raket.ph/kutonn" },
        ],
      },
      // Calculator
      display: "",
    };
  },
  methods: {
    toggleHobby(index) {
      this.hobbies[index].active = !this.hobbies[index].active;
    },

    // Calculator Methods
    appendNumber(n) {
      this.display += n;
    },
    appendDot() {
      if (!this.display.endsWith(".")) this.display += ".";
    },
    appendOperator(op) {
      if (this.display === "") return;
      const lastChar = this.display.slice(-1);
      if ("+-*/".includes(lastChar)) {
        this.display = this.display.slice(0, -1) + op;
      } else {
        this.display += op;
      }
    },
    clearAll() {
      this.display = "";
    },
    deleteLast() {
      this.display = this.display.slice(0, -1);
    },
    calculate() {
      try {
        this.display = eval(this.display).toString();
      } catch {
        this.display = "Error";
      }
    },
  },
};
</script>

<style scoped>
.page {
  padding: 1.5rem;
  font-family: Arial, sans-serif;
}

h1 {
  text-align: center;
  margin-bottom: 2rem;
}

/* Hobbies Section */
.hobbies {
  margin-bottom: 3rem;
  text-align: center; /* center the heading and description */
}

.hobby-cards {
  display: flex;            /* use flexbox for easy centering */
  flex-wrap: wrap;          /* allow multiple rows */
  justify-content: center;  /* center items horizontally */
  gap: 1rem;                /* spacing between cards */
}

.hobby-card {
  flex: 0 1 180px;          /* fixed min width, do not stretch */
  background: #f3f3f3;
  padding: 1rem;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.3s ease;
  text-align: center;       /* center text inside each card */
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.hobby-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}

.hobby-card.active {
  background: #dbeafe;
}


/* Resume */
.resume h2 { margin-bottom: 1rem; }
.resume-content {
  background: #f9f9f9;
  padding: 1rem 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
}
.resume-content ul { margin-left: 1.2rem; margin-bottom: 1rem; }
.resume-content a { color: #2563eb; text-decoration: none; }
.resume-content a:hover { text-decoration: underline; }

/* Calculator */
.calculator {
  margin-top: 3rem;
  text-align: center;
}
.calculator-container {
  display: inline-block;
  background: #f3f3f3;
  padding: 1rem;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.2);
}
.calculator-container input {
  width: 100%;
  text-align: right;
  padding: 0.5rem;
  margin-bottom: 0.5rem;
  font-size: 1.2rem;
  border-radius: 6px;
  border: 1px solid #ccc;
}
.buttons {
  display: grid;
  grid-template-columns: repeat(4, 60px);
  gap: 0.5rem;
  justify-content: center;
}
.buttons button {
  padding: 1rem;
  font-size: 1.2rem;
  border-radius: 6px;
  border: none;
  cursor: pointer;
  background: #5D8AA8;
  color: white;
  transition: all 0.2s ease;
}
.buttons button:hover { background: #004F98; }
button.zero { grid-column: span 2; }
button.equals { grid-row: span 2; background: #10b981; }
button.equals:hover { background: #059669; }
</style>
