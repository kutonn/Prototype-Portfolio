<template>
  <div class="page fade-in">
    <div class="card profile-card">
      <img :src="profileImg" alt="Profile" class="profile-img" />

      <h1>Elton Jhon M. Pabuayon</h1>
      <p class="role">Computer Engineer</p>

      <p class="bio">
       A Computer Engineer who's fond in digital art, and layout designs with a pinch of curiosity towards computer hardware and software.
      </p>

      <div class="social-links">
        <!-- Facebook -->
        <a href="https://web.facebook.com/ltn.jhn.pbyn" target="_blank" aria-label="Facebook">
          <svg viewBox="0 0 24 24">
            <path
              d="M22 12a10 10 0 1 0-11.5 9.9v-7h-2v-3h2V9.5c0-2 1.2-3.1 3-3.1.9 0 1.8.1 1.8.1v2h-1c-1 0-1.3.6-1.3 1.2V12h2.3l-.4 3h-1.9v7A10 10 0 0 0 22 12"
            />
          </svg>
        </a>

        <!-- GitHub -->
        <a href="https://github.com/kutonn" target="_blank" aria-label="GitHub">
          <svg viewBox="0 0 24 24">
            <path
              d="M12 .5a12 12 0 0 0-3.8 23.4c.6.1.8-.2.8-.5v-1.8c-3.3.7-4-1.4-4-1.4-.6-1.4-1.4-1.8-1.4-1.8-1.1-.8.1-.8.1-.8 1.2.1 1.9 1.3 1.9 1.3 1.1 1.9 2.9 1.3 3.6 1 .1-.8.4-1.3.7-1.6-2.6-.3-5.3-1.3-5.3-5.9 0-1.3.5-2.4 1.2-3.3-.1-.3-.5-1.5.1-3.1 0 0 1-.3 3.4 1.3a11.8 11.8 0 0 1 6.2 0c2.4-1.6 3.4-1.3 3.4-1.3.6 1.6.2 2.8.1 3.1.8.9 1.2 2 1.2 3.3 0 4.6-2.7 5.6-5.3 5.9.4.3.8 1 .8 2v3c0 .3.2.6.8.5A12 12 0 0 0 12 .5"
            />
          </svg>
        </a>

        <!-- LinkedIn -->
        <a href="https://www.linkedin.com/in/elton-jhon-m-pabuayon-16a624310" target="_blank" aria-label="LinkedIn">
          <svg viewBox="0 0 24 24">
            <path
              d="M4.98 3.5a2.5 2.5 0 1 0 0 5 2.5 2.5 0 0 0 0-5ZM3 8.98h4v12H3ZM9 8.98h3.8v1.6h.1c.5-.9 1.8-1.8 3.6-1.8 3.9 0 4.6 2.5 4.6 5.7v6.5h-4v-5.7c0-1.4 0-3.2-2-3.2s-2.3 1.5-2.3 3.1v5.8H9Z"
            />
          </svg>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import profileImg from '../assets/profile.png'

export default {
  name: 'Profile',
  data() {
    return {
      profileImg
    }
  }
}
</script>

<style scoped>
.profile-card {
  text-align: center;
}

.profile-img {
  width: 140px;
  height: 140px;
  object-fit: cover;
  border-radius: 50%;
  margin-bottom: 1rem;
}

.role {
  color: #6b7280;
  margin-bottom: 1rem;
}

.bio {
  max-width: 600px;
  margin: 0 auto 1.5rem;
  font-size: 0.95rem;
  color: #374151;
}

.social-links {
  display: flex;
  justify-content: center;
  gap: 1.2rem;
}

.social-links a {
  width: 36px;
  height: 36px;
  display: grid;
  place-items: center;
  border-radius: 50%;
  background: #f3f4f6;
  transition: background 0.2s ease, transform 0.2s ease;
}

.social-links a:hover {
  background: #e5e7eb;
  transform: translateY(-2px);
}

.social-links svg {
  width: 18px;
  height: 18px;
  fill: #1f2937;
}
</style>
