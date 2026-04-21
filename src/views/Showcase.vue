<template>
  <div class="page fade-in">
    <h1><center>Showcase Works</center></h1>

    <!-- Project Cards -->
    <div class="cards">
      <div class="card" v-for="project in projects" :key="project.id">
        <h3>{{ project.title }}</h3>
        <p>{{ project.description }}</p>

        <!-- Buttons -->
        <div class="buttons">
          <button
            v-for="(link, index) in project.links"
            :key="index"
            @click="openPdf(link.url)"
          >
            {{ link.text }}
          </button>
        </div>
      </div>
    </div>

    <!-- PDF Preview -->
    <div v-if="activePdf" class="pdf-preview">
      <button class="close-btn" @click="activePdf = null">Close Preview</button>

      <iframe
        :src="activePdf + '#toolbar=0&navpanes=0'"
        frameborder="0"
      ></iframe>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Showcase',
  data() {
    return {
      activePdf: null,
      projects: [
        {
          id: 1,
          title: 'Personal Projects',
          description: 'Layouts and designs for business purposes.',
          links: [
            {
              text: 'View Portfolio PDF',
              url: '/pdfs/personalprojects.pdf'
            }
          ]
        },
        {
          id: 2,
          title: 'Commissions',
          description: 'Customer-requested designs and layouts.',
          links: [
            {
              text: 'View Portfolio PDF',
              url: '/pdfs/commission.pdf'
            }
          ]
        }
      ]
    }
  },
  methods: {
    openPdf(url) {
      this.activePdf = url
    }
  }
}
</script>

<style scoped>
.page {
  padding: 2rem;
}

.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
}

/* Card */
.card {
  border: 1px solid #e5e7eb;
  border-radius: 12px;
  padding: 1.25rem;
  background: #fff;
}

/* Buttons */
.buttons {
  margin-top: 1rem;
  display: flex;
  justify-content: center;
}

button {
  background: #5D8AA8;
  color: white;
  border: none;
  padding: 0.5rem 1.25rem;
  border-radius: 6px;
  cursor: pointer;
  font-size: 0.9rem;
}

button:hover {
  background: #004F98;
}

/* PDF Preview */
.pdf-preview {
  margin-top: 2rem;
  border: 1px solid #ddd;
  border-radius: 10px;
  overflow: hidden;
}

.pdf-preview iframe {
  width: 100%;
  height: 80vh;
}

.close-btn {
  background: #ef4444;
  margin: 0.5rem;
}
</style>
