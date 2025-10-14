<script setup>
import { ref, onMounted, watch } from "vue";

const confetti = ref([]);
const currentPage = ref(0);
const typedText = ref("");
const showCursor = ref(true);
const isTyping = ref(false);
let typingInterval = null;

// Define pages with their content
const pages = [
  {
    image: "/em_be.jpeg", // Placeholder - add em_be.jpg to /public folder
    text: "23 năm trước, có một em bé ra đời...",
    title: "🎂 Once Upon a Time...",
  },
  {
    image: "/xinh_dep.jpeg", // Placeholder - add xinh_dep.jpeg to /public folder
    text: "Cô ấy lớn lên, dần dần, dần dần",
    title: "💫 Growing Up...",
  },
  {
    image: "/cow_and_human.jpeg", // Using cow image for the cow joke!
    text: "Khi gặp tôi, chúng tôi đứng chung một khung hình thì sẽ luôn có 1 người 1 bò. Nhưng cô ấy là người còn tôi là bò :(",
    title: "🐄 The Perfect Duo...",
  },
  {
    image: "/MinhThu.jpeg",
    text: "Tuổi mới... Chúc Minh Thu luôn mạnh khoẻ, xinh đẹp, gặt được các thành tựu mới và bên cạnh tôi hô hô hô",
    title: "🎉 HAPPY BIRTHDAY MINH THU! 🎉",
  },
];

onMounted(() => {
  // Create confetti
  for (let i = 0; i < 50; i++) {
    confetti.value.push({
      id: i,
      left: Math.random() * 100,
      delay: Math.random() * 5,
      duration: 3 + Math.random() * 2,
      color: ["#ff6b6b", "#4ecdc4", "#45b7d1", "#ffd93d", "#ff6fb5"][
        Math.floor(Math.random() * 5)
      ],
    });
  }

  // Start typing for the first page
  setTimeout(() => {
    startTyping(pages[0].text);
  }, 500);

  // Cursor blink
  setInterval(() => {
    if (isTyping.value) {
      showCursor.value = !showCursor.value;
    }
  }, 500);
});

// Watch for page changes
watch(currentPage, (newPage) => {
  typedText.value = "";
  showCursor.value = true;
  startTyping(pages[newPage].text);
});

const startTyping = (text) => {
  if (typingInterval) {
    clearInterval(typingInterval);
  }

  typedText.value = "";
  isTyping.value = true;
  let index = 0;
  const typingSpeed = 50;

  typingInterval = setInterval(() => {
    if (index < text.length) {
      typedText.value += text[index];
      index++;
    } else {
      clearInterval(typingInterval);
      isTyping.value = false;
      showCursor.value = false;
    }
  }, typingSpeed);
};

const nextPage = () => {
  if (currentPage.value < pages.length - 1) {
    currentPage.value++;
  }
};

const prevPage = () => {
  if (currentPage.value > 0) {
    currentPage.value--;
  }
};
</script>

<template>
  <div class="birthday-container">
    <!-- Confetti -->
    <div class="confetti-wrapper">
      <div
        v-for="item in confetti"
        :key="item.id"
        class="confetti"
        :style="{
          left: item.left + '%',
          animationDelay: item.delay + 's',
          animationDuration: item.duration + 's',
          backgroundColor: item.color,
        }"
      />
    </div>

    <!-- Page Content -->
    <div class="page-container">
      <!-- Current Page -->
      <transition name="fade" mode="out-in">
        <div :key="currentPage" class="page">
          <!-- Title -->
          <h1 class="page-title">{{ pages[currentPage].title }}</h1>

          <!-- Image -->
          <div class="image-container">
            <img
              :src="pages[currentPage].image"
              :alt="`Page ${currentPage + 1}`"
              class="page-image"
            />
            <div class="sparkle sparkle-1">✨</div>
            <div class="sparkle sparkle-2">✨</div>
            <div class="sparkle sparkle-3">✨</div>
            <div class="sparkle sparkle-4">✨</div>
          </div>

          <!-- Typing Text -->
          <div class="typing-container">
            <p class="typing-message">
              {{ typedText }}<span class="cursor" v-if="showCursor">|</span>
            </p>
          </div>
        </div>
      </transition>

      <!-- Navigation Buttons -->
      <div class="navigation">
        <button
          v-if="currentPage > 0"
          @click="prevPage"
          class="nav-button prev-button"
        >
          ← Trước
        </button>

        <!-- Page Indicator -->
        <div class="page-indicator">
          <span
            v-for="(page, index) in pages"
            :key="index"
            class="dot"
            :class="{ active: currentPage === index }"
          ></span>
        </div>

        <button
          v-if="currentPage < pages.length - 1"
          @click="nextPage"
          class="nav-button next-button"
        >
          Tiếp →
        </button>
      </div>

      <!-- Floating Animals -->
      <div class="animals">
        <img src="/meo1.png" alt="Cat 1" class="animal cat1" />
        <img src="/meo2.png" alt="Cat 2" class="animal cat2" />
        <img src="/cho.png" alt="Dog" class="animal dog" />
        <img src="/bo.png" alt="Cow" class="animal cow" />
      </div>
    </div>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.birthday-container {
  width: 100vw;
  height: 100vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
  position: fixed;
  top: 0;
  left: 0;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0;
}

/* Confetti Animation */
.confetti-wrapper {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  overflow: hidden;
}

.confetti {
  position: absolute;
  width: 10px;
  height: 10px;
  top: -10px;
  animation: fall linear infinite;
}

@keyframes fall {
  to {
    transform: translateY(100vh) rotate(360deg);
  }
}

/* Page Container */
.page-container {
  width: 100%;
  height: 100%;
  text-align: center;
  z-index: 10;
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
}

.page {
  animation: fadeIn 0.5s ease-in-out;
  width: 100%;
  max-width: 900px;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Fade transition */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease, transform 0.3s ease;
}

.fade-enter-from {
  opacity: 0;
  transform: translateX(30px);
}

.fade-leave-to {
  opacity: 0;
  transform: translateX(-30px);
}

/* Page Title */
.page-title {
  font-size: 2.5rem;
  color: #fff;
  text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.3);
  margin-bottom: 2rem;
  animation: bounce 2s ease-in-out infinite;
  font-weight: bold;
}

@keyframes bounce {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

/* Image Container */
.image-container {
  position: relative;
  display: inline-block;
  margin: 2rem auto;
  animation: pulse 3s ease-in-out infinite;
}

.page-image {
  width: 300px;
  height: 300px;
  border-radius: 20px;
  border: 8px solid #fff;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
  object-fit: cover;
}

@keyframes pulse {
  0%,
  100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.03);
  }
}

.sparkle {
  position: absolute;
  font-size: 2rem;
  animation: sparkle 1.5s ease-in-out infinite;
  pointer-events: none;
}

.sparkle-1 {
  top: -10px;
  left: -10px;
  animation-delay: 0s;
}
.sparkle-2 {
  top: -10px;
  right: -10px;
  animation-delay: 0.3s;
}
.sparkle-3 {
  bottom: -10px;
  left: -10px;
  animation-delay: 0.6s;
}
.sparkle-4 {
  bottom: -10px;
  right: -10px;
  animation-delay: 0.9s;
}

@keyframes sparkle {
  0%,
  100% {
    transform: scale(1) rotate(0deg);
    opacity: 1;
  }
  50% {
    transform: scale(1.5) rotate(180deg);
    opacity: 0.5;
  }
}

/* Typing Container */
.typing-container {
  margin: 2rem auto;
  padding: 0 20px;
  max-width: 700px;
}

.typing-message {
  font-size: 1.5rem;
  color: #fff;
  line-height: 2;
  text-align: center;
  background: rgba(0, 0, 0, 0.3);
  padding: 2rem;
  border-radius: 20px;
  backdrop-filter: blur(10px);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
  white-space: pre-wrap;
  word-wrap: break-word;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  min-height: 120px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.cursor {
  display: inline-block;
  width: 3px;
  height: 1.5rem;
  background-color: #ffd93d;
  margin-left: 3px;
  animation: blink 1s step-end infinite;
}

@keyframes blink {
  50% {
    opacity: 0;
  }
}

/* Navigation */
.navigation {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 2rem;
  margin-top: 3rem;
  flex-wrap: wrap;
}

.nav-button {
  padding: 15px 35px;
  font-size: 1.2rem;
  font-weight: bold;
  color: #fff;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border: 3px solid #fff;
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  text-transform: uppercase;
  letter-spacing: 1px;
}

.nav-button:hover {
  transform: translateY(-3px) scale(1.05);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
  background: linear-gradient(135deg, #764ba2 0%, #f093fb 100%);
}

.nav-button:active {
  transform: translateY(0);
}

/* Page Indicator */
.page-indicator {
  display: flex;
  gap: 12px;
  align-items: center;
}

.dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.5);
  transition: all 0.3s ease;
  cursor: pointer;
}

.dot.active {
  background: #ffd93d;
  width: 16px;
  height: 16px;
  box-shadow: 0 0 10px #ffd93d;
}

/* Floating Animals */
.animals {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
}

.animal {
  position: absolute;
  width: 80px;
  height: 80px;
  object-fit: contain;
  filter: drop-shadow(2px 2px 4px rgba(0, 0, 0, 0.2));
}

.cat1 {
  top: 15%;
  left: 10%;
  animation: float 3s ease-in-out infinite;
}

.cat2 {
  top: 20%;
  right: 10%;
  animation: float 4s ease-in-out infinite 0.5s;
}

.dog {
  bottom: 20%;
  left: 15%;
  animation: float 3.5s ease-in-out infinite 1s;
}

.cow {
  bottom: 25%;
  right: 15%;
  animation: float 4s ease-in-out infinite 1.5s;
}

@keyframes float {
  0%,
  100% {
    transform: translateY(0) rotate(0deg);
  }
  50% {
    transform: translateY(-30px) rotate(10deg);
  }
}

/* Responsive Design */
@media (max-width: 768px) {
  .page-title {
    font-size: 1.8rem;
  }

  .page-image {
    width: 220px;
    height: 220px;
  }

  .typing-message {
    font-size: 1.1rem;
    padding: 1.5rem;
    min-height: 100px;
  }

  .nav-button {
    padding: 12px 25px;
    font-size: 1rem;
  }

  .navigation {
    gap: 1rem;
  }

  .animal {
    width: 50px;
    height: 50px;
  }

  .sparkle {
    font-size: 1.5rem;
  }
}
</style>
