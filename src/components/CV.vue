<template>
  <div class="cv-container">
    <!-- Animated Background -->
    <div class="bg-animation">
      <div class="bg-shape shape-1"></div>
      <div class="bg-shape shape-2"></div>
      <div class="bg-shape shape-3"></div>
    </div>

    <!-- CV Content -->
    <div class="cv-content">
      <!-- Header -->
      <div class="cv-header">
        <div class="photo-container">
          <img src="/mt.jpeg" alt="CV Photo" class="cv-photo" />
          <div class="photo-frame"></div>
          <div class="sparkles">
            <span class="sparkle">✨</span>
            <span class="sparkle">⭐</span>
            <span class="sparkle">💫</span>
          </div>
        </div>
        <h1 class="cv-name">MINH THU</h1>
        <p class="cv-title">Ứng viên cho vị trí: Ngủ cả ngày 😴</p>
        <p class="cv-intro">
          Xin chào! Tôi là Minh Thu, tôi muốn đi ngủ, tôi muốn ngủ thoải mái mà
          không cần quan tâm báo thức 😗.
        </p>
      </div>

      <!-- Main Content -->
      <div class="cv-body">
        <!-- Education Section -->
        <section class="cv-section">
          <h2 class="section-title">
            <span class="icon">🎓</span>
            Học vấn
          </h2>
          <div class="section-content">
            <div class="info-card">
              <p class="info-text">
                <strong>Tốt nghiệp Đại học Dược Hà Nội</strong>
              </p>
              <p class="info-description">
                Trong quá trình học tập tại trường đại học, tôi đã được trang bị
                những kiến thức chuyên sâu về cách luộc rau má. Hãy cho tôi một
                vài lá rau má, tôi sẽ biến nó thành một món ăn ngon miệng từ
                chiếc máy cô quay của mình 😍.
              </p>
            </div>
          </div>
        </section>

        <!-- Skills Section -->
        <section class="cv-section">
          <h2 class="section-title">
            <span class="icon">🛹</span>
            Kỹ năng đặc biệt
          </h2>
          <div class="section-content">
            <p class="skills-intro">
              Tôi sở hữu những kỹ năng vận động đặc biệt mà không phải ai cũng
              có. Đây là những kỹ năng tôi đã rèn luyện và phát triển qua nhiều
              năm, thể hiện sự khéo léo, cân bằng và khả năng kiểm soát cơ thể
              tuyệt vời.
            </p>
            <div class="skills-list">
              <div class="skill-item" v-for="skill in skills" :key="skill.name">
                <div class="skill-header">
                  <span class="skill-name">{{ skill.name }}</span>
                  <span class="skill-percentage">{{ skill.level }}%</span>
                </div>
                <div class="skill-bar-container">
                  <div
                    class="skill-bar"
                    :style="{ width: skill.level + '%' }"
                    :class="skill.class"
                    :data-width="skill.level + '%'"
                  >
                    <div class="skill-bar-fill"></div>
                  </div>
                </div>
                <p class="skill-description">{{ skill.description }}</p>
              </div>
            </div>
          </div>
        </section>

        <!-- Experience Section -->
        <section class="cv-section">
          <h2 class="section-title">
            <span class="icon">🐕</span>
            Kinh nghiệm làm việc
          </h2>
          <div class="section-content">
            <div class="info-card experience-card">
              <p class="info-text">
                <strong>Hong thèm ghi</strong>
              </p>
            </div>
          </div>
        </section>

        <!-- Interests Section -->
        <section class="cv-section">
          <h2 class="section-title">
            <span class="icon">❤️</span>
            Sở thích và đam mê
          </h2>
          <div class="section-content">
            <div class="interests-container">
              <div class="interest-item">
                <span class="interest-icon">🐕</span>
                <div class="interest-content">
                  <strong>Chó, mèo</strong>
                  <p>
                    Mang chó đến đây tôi sẽ bắt Sơn sang dọn cứt giúp, bạn không
                    cần lo nhiều. Dù Sơn là chó nhưng tôi chê 😩
                  </p>
                </div>
              </div>

              <div class="interest-item">
                <span class="interest-icon">🛹</span>
                <div class="interest-content">
                  <strong>Vận động</strong>
                  <p>
                    Tôi đam mê các hoạt động vận động như đánh võng, bốc đầu,
                    bốc đít và tạt đầu. Những hoạt động này giúp tôi rèn luyện
                    sự cân bằng, phản xạ và sự tự tin, giúp tôi ngủ ngon hơn vào
                    buổi tối !!!
                  </p>
                </div>
              </div>
            </div>
          </div>
        </section>

        <!-- IT Knowledge Section -->
        <section class="cv-section highlight-section">
          <h2 class="section-title">
            <span class="icon">💻</span>
            Kiến thức Công nghệ thông tin
          </h2>
          <div class="it-knowledge">
            <div class="zero-display">
              <span class="big-zero">0</span>
              <p class="zero-text">Hoàn toàn không biết gì về IT</p>
            </div>
            <div class="it-description">
              <p>
                Tôi thừa nhận một cách thẳng thắn rằng kiến thức về công nghệ
                thông tin của tôi hoàn toàn bằng không. Tôi không biết lập
                trình, không hiểu về phần mềm, và cũng không quen thuộc với các
                công cụ công nghệ hiện đại. Tuy nhiên, tôi tin rằng sự trung
                thực là điều quan trọng, và tôi sẵn sàng học hỏi nếu cần thiết.
                Mặc dù không có kiến thức IT, nhưng tôi có những kỹ năng khác mà
                có thể đóng góp giá trị cho công ty 😏.
              </p>
              <p class="it-note">
                <strong>Lưu ý:</strong> Nếu vị trí công việc yêu cầu kiến thức
                IT, tôi cũng hong thèm học hỏi, hãy đè đầu thằng Sơn ra 😒.
              </p>
            </div>
          </div>
        </section>

        <!-- Position Section -->
        <section class="cv-section position-section">
          <h2 class="section-title">
            <span class="icon">🎯</span>
            Vị trí ứng tuyển
          </h2>
          <div class="position-card">
            <h3 class="position-title">NGỦ CẢ NGÀY</h3>
            <p class="position-description">
              Tôi đang tìm kiếm một vị trí công việc cho phép tôi phát huy tối
              đa khả năng ngủ của mình. Đây không chỉ là một sở thích mà còn là
              một tài năng đặc biệt mà tôi đã rèn luyện qua nhiều năm. Tôi có
              thể ngủ từ sáng đến tối, từ tối đến sáng, và thậm chí có thể ngủ
              liên tục trong nhiều giờ mà không cần thức dậy.
            </p>
            <div class="position-benefits">
              <h4>Lợi ích khi tuyển dụng tôi:</h4>
              <ul>
                <li>
                  ✅ Tiết kiệm chi phí điện năng (tôi không cần máy tính, đèn,
                  hay thiết bị điện tử)
                </li>
                <li>✅ Không tạo ra tiếng ồn trong văn phòng</li>
                <li>✅ Luôn có mặt tại nơi làm việc (vì tôi sẽ ngủ ở đó)</li>
                <li>✅ Không cần phòng họp hay không gian làm việc phức tạp</li>
                <li>
                  ✅ Tạo không khí yên tĩnh, thư giãn cho môi trường làm việc
                </li>
              </ul>
            </div>
            <p class="position-closing">
              Tôi tin rằng với khả năng ngủ đặc biệt của mình, tôi có thể đóng
              góp tích cực vào môi trường làm việc và giúp công ty tiết kiệm
              nhiều chi phí không cần thiết. Hãy cho tôi cơ hội để chứng minh
              điều đó! 😴💤
            </p>
          </div>
        </section>

        <!-- Interviewer Section -->
        <section class="cv-section interviewer-section">
          <h2 class="section-title">
            <span class="icon">👔</span>
            Yêu cầu phỏng vấn
          </h2>
          <div class="interviewer-card">
            <p class="interviewer-text">
              Để đảm bảo chất lượng và hiệu quả của buổi phỏng vấn, tôi có một
              yêu cầu đặc biệt:
            </p>
            <p class="interviewer-name">Nguyễn Hồng Sơn</p>
            <div class="interviewer-badge">✨ Exclusive Interviewer ✨</div>
            <div class="interviewer-details">
              <p>
                Tôi chỉ chấp nhận phỏng vấn với anh
                <strong>Nguyễn Hồng Sơn</strong>. Đây không phải là một yêu cầu
                tùy tiện mà là một quyết định có cân nhắc vì tôi ghét hắn 😏.
              </p>
              <p>
                Nếu công ty không thể đáp ứng yêu cầu này, tôi rất tiếc nhưng sẽ
                không thể tham gia phỏng vấn. Tuy nhiên, nếu có thể sắp xếp, tôi
                sẽ rất vui mừng được gặp gỡ và trao đổi với anh Nguyễn Hồng Sơn
                😗
              </p>
            </div>
          </div>
        </section>
      </div>

      <!-- Footer -->
      <div class="cv-footer">
        <p class="footer-text">"Tôi buồn ngủ. Hãy cho tôi cơ hội!"</p>
        <div class="footer-decoration">💤😴💤</div>
      </div>
    </div>

    <!-- Floating Elements -->
    <div class="floating-elements">
      <div class="floating-icon">🛹</div>
      <div class="floating-icon">🐕</div>
      <div class="floating-icon">🐱</div>
      <div class="floating-icon">😴</div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

const skills = ref([
  {
    name: "Đánh võng",
    level: 95,
    class: "skill-expert",
    description:
      "Kỹ năng đánh võng của tôi đã đạt đến trình độ chuyên nghiệp. Tôi có thể đánh võng một cách mượt mà, cân bằng và kiểm soát tốt trong mọi tình huống. Mặc dù vậy nhưng tôi thường đi theo trí tuệ chứ không thể hiện nhiều kỹ năng này 😘",
  },
  {
    name: "Bốc đầu",
    level: 90,
    class: "skill-advanced",
    description:
      "Tôi có thể bốc đầu một cách ổn định và duy trì trong thời gian dài. Đây là một kỹ năng đòi hỏi sự kiểm soát cơ thể tuyệt vời. Nhưng tôi chưa bao giờ hướng dẫn Sơn cả!!",
  },
  {
    name: "Bốc đít",
    level: 88,
    class: "skill-advanced",
    description:
      "Bốc đít là một kỹ năng khó và tôi đã thành thạo nó trong mơ. Tôi mới chỉ khuyên người khác nhưng tôi chưa làm 😩",
  },
  {
    name: "Tạt đầu",
    level: 92,
    class: "skill-expert",
    description:
      "Tạt đầu là một trong những kỹ năng mạnh nhất của tôi. Tôi có thể thực hiện động tác này với độ chính xác cao và phản xạ nhanh. Xe tải, container? không, tàu hoả và máy bay là 2 thể loại mà tôi yêu thích nhất 😍",
  },
  {
    name: "Ngủ sâu",
    level: 100,
    class: "skill-master",
    description:
      "Đây là kỹ năng đặc biệt nhất của tôi. Tôi có thể ngủ sâu và chất lượng nếu như không có tiếng ồn nào dù là nhỏ nhất. Sữa không sủa và lừa đảo không gọi lúc sáng sớm 🥲",
  },
]);

onMounted(() => {
  // Animate skill bars on mount
  setTimeout(() => {
    const skillBars = document.querySelectorAll(".skill-bar");
    skillBars.forEach((bar, index) => {
      const width = bar.style.width || bar.getAttribute("data-width") || "0%";
      bar.setAttribute("data-width", width);
      bar.style.width = "0%";
      setTimeout(() => {
        bar.style.transition = "width 1.5s ease-out";
        bar.style.width = width;
      }, 100 + index * 100);
    });
  }, 500);
});
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.cv-container {
  min-height: 100vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
  position: relative;
  overflow-x: hidden;
  padding: 20px;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

/* Animated Background */
.bg-animation {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
  overflow: hidden;
}

.bg-shape {
  position: absolute;
  border-radius: 50%;
  opacity: 0.1;
  animation: float 20s infinite ease-in-out;
}

.shape-1 {
  width: 300px;
  height: 300px;
  background: #ffd93d;
  top: 10%;
  left: 10%;
  animation-delay: 0s;
}

.shape-2 {
  width: 200px;
  height: 200px;
  background: #4ecdc4;
  top: 60%;
  right: 15%;
  animation-delay: 5s;
}

.shape-3 {
  width: 250px;
  height: 250px;
  background: #ff6b6b;
  bottom: 10%;
  left: 20%;
  animation-delay: 10s;
}

@keyframes float {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  33% {
    transform: translate(30px, -30px) rotate(120deg);
  }
  66% {
    transform: translate(-20px, 20px) rotate(240deg);
  }
}

/* CV Content */
.cv-content {
  max-width: 900px;
  margin: 0 auto;
  background: rgba(255, 255, 255, 0.95);
  border-radius: 30px;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  padding: 40px;
  position: relative;
  z-index: 1;
  backdrop-filter: blur(10px);
  animation: slideUp 0.8s ease-out;
}

@keyframes slideUp {
  from {
    opacity: 0;
    transform: translateY(50px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Header */
.cv-header {
  text-align: center;
  margin-bottom: 40px;
  padding-bottom: 30px;
  border-bottom: 3px solid #667eea;
}

.photo-container {
  position: relative;
  display: inline-block;
  margin-bottom: 20px;
}

.cv-photo {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  object-fit: cover;
  border: 8px solid #667eea;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  animation: photoPulse 3s ease-in-out infinite;
}

@keyframes photoPulse {
  0%,
  100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.05);
  }
}

.photo-frame {
  position: absolute;
  top: -10px;
  left: -10px;
  right: -10px;
  bottom: -10px;
  border: 3px solid #ffd93d;
  border-radius: 50%;
  animation: rotate 10s linear infinite;
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.sparkles {
  position: absolute;
  top: -20px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 20px;
}

.sparkle {
  font-size: 1.5rem;
  animation: sparkle 2s ease-in-out infinite;
}

.sparkle:nth-child(2) {
  animation-delay: 0.5s;
}

.sparkle:nth-child(3) {
  animation-delay: 1s;
}

@keyframes sparkle {
  0%,
  100% {
    opacity: 1;
    transform: scale(1);
  }
  50% {
    opacity: 0.5;
    transform: scale(1.3);
  }
}

.cv-name {
  font-size: 3rem;
  color: #667eea;
  margin-bottom: 10px;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
  animation: nameGlow 2s ease-in-out infinite;
}

@keyframes nameGlow {
  0%,
  100% {
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
  }
  50% {
    text-shadow: 2px 2px 20px rgba(102, 126, 234, 0.5);
  }
}

.cv-title {
  font-size: 1.3rem;
  color: #764ba2;
  font-weight: 600;
  margin-bottom: 20px;
}

.cv-intro {
  font-size: 1rem;
  color: #555;
  line-height: 1.8;
  text-align: justify;
  max-width: 800px;
  margin: 20px auto 0;
  padding: 20px;
  background: rgba(102, 126, 234, 0.05);
  border-radius: 10px;
  border-left: 4px solid #667eea;
}

/* Sections */
.cv-section {
  margin-bottom: 35px;
  animation: fadeIn 0.6s ease-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateX(-20px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

.section-title {
  font-size: 1.8rem;
  color: #667eea;
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  gap: 10px;
  border-left: 5px solid #ffd93d;
  padding-left: 15px;
}

.icon {
  font-size: 2rem;
}

.section-content {
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
  padding: 20px;
  border-radius: 15px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.info-card {
  background: white;
  padding: 20px;
  border-radius: 10px;
  margin-bottom: 15px;
  border-left: 4px solid #667eea;
  transition: transform 0.3s ease;
}

.info-card:hover {
  transform: translateX(5px);
}

.info-text {
  font-size: 1.1rem;
  color: #333;
  margin-bottom: 5px;
}

.info-subtext {
  font-size: 0.95rem;
  color: #666;
  margin-bottom: 10px;
}

.info-description {
  font-size: 0.95rem;
  color: #555;
  line-height: 1.8;
  text-align: justify;
  margin-top: 10px;
}

.experience-period {
  font-size: 0.9rem;
  color: #667eea;
  font-weight: normal;
  margin-left: 10px;
}

.experience-list {
  margin-top: 15px;
  padding-left: 20px;
}

.experience-list li {
  margin-bottom: 8px;
  color: #555;
  line-height: 1.6;
}

/* Skills */
.skills-intro {
  font-size: 1rem;
  color: #555;
  line-height: 1.8;
  margin-bottom: 25px;
  text-align: justify;
}

.skills-list {
  display: flex;
  flex-direction: column;
  gap: 25px;
}

.skill-item {
  background: white;
  padding: 20px;
  border-radius: 10px;
  border-left: 4px solid #667eea;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.skill-item:hover {
  transform: translateX(5px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

.skill-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
}

.skill-name {
  font-size: 1.2rem;
  font-weight: 600;
  color: #667eea;
}

.skill-percentage {
  font-size: 1rem;
  font-weight: bold;
  color: #764ba2;
}

.skill-bar-container {
  width: 100%;
  height: 25px;
  background: #e0e0e0;
  border-radius: 15px;
  overflow: hidden;
  margin-bottom: 10px;
  box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.1);
}

.skill-bar {
  height: 100%;
  border-radius: 15px;
  position: relative;
  overflow: hidden;
  width: 0%;
}

.skill-bar-fill {
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
  border-radius: 15px;
  position: relative;
  animation: shimmer 2s infinite;
}

.skill-bar-fill::after {
  content: "";
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(
    90deg,
    transparent,
    rgba(255, 255, 255, 0.3),
    transparent
  );
  animation: slide 2s infinite;
}

@keyframes shimmer {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0.9;
  }
}

@keyframes slide {
  0% {
    left: -100%;
  }
  100% {
    left: 100%;
  }
}

.skill-expert .skill-bar-fill {
  background: linear-gradient(90deg, #4ecdc4 0%, #44a08d 100%);
}

.skill-advanced .skill-bar-fill {
  background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
}

.skill-master .skill-bar-fill {
  background: linear-gradient(90deg, #ffd93d 0%, #f6c23e 50%, #ff6b6b 100%);
  animation: masterGlow 2s infinite;
}

@keyframes masterGlow {
  0%,
  100% {
    box-shadow: 0 0 10px rgba(255, 217, 61, 0.5);
  }
  50% {
    box-shadow: 0 0 20px rgba(255, 217, 61, 0.8);
  }
}

.skill-description {
  font-size: 0.9rem;
  color: #666;
  line-height: 1.6;
  margin-top: 8px;
  text-align: justify;
}

/* Experience */
.experience-card {
  background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
}

/* Interests */
.interests-intro {
  font-size: 1rem;
  color: #555;
  line-height: 1.8;
  margin-bottom: 25px;
  text-align: justify;
}

.interests-container {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.interest-item {
  background: white;
  padding: 20px;
  border-radius: 15px;
  display: flex;
  align-items: flex-start;
  gap: 15px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  border-left: 4px solid #667eea;
}

.interest-item:hover {
  transform: translateX(5px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
}

.interest-icon {
  font-size: 2.5rem;
  flex-shrink: 0;
}

.interest-content {
  flex: 1;
}

.interest-content strong {
  display: block;
  font-size: 1.2rem;
  color: #667eea;
  margin-bottom: 8px;
}

.interest-content p {
  font-size: 0.95rem;
  color: #555;
  line-height: 1.7;
  text-align: justify;
  margin: 0;
}

/* IT Knowledge */
.highlight-section {
  background: linear-gradient(135deg, #ff6b6b 0%, #ee5a6f 100%);
  padding: 30px;
  border-radius: 20px;
  color: white;
}

.highlight-section .section-title {
  color: white;
  border-left-color: white;
}

.it-knowledge {
  text-align: center;
  padding: 30px;
}

.big-zero {
  font-size: 8rem;
  font-weight: bold;
  display: block;
  line-height: 1;
  text-shadow: 5px 5px 10px rgba(0, 0, 0, 0.3);
  animation: zeroPulse 2s ease-in-out infinite;
}

@keyframes zeroPulse {
  0%,
  100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
}

.zero-text {
  font-size: 1.3rem;
  margin-top: 20px;
  font-weight: 600;
}

.it-description {
  margin-top: 30px;
  text-align: left;
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
}

.it-description p {
  font-size: 1rem;
  line-height: 1.8;
  margin-bottom: 15px;
}

.it-note {
  background: rgba(255, 255, 255, 0.2);
  padding: 15px;
  border-radius: 10px;
  margin-top: 20px;
  border-left: 4px solid white;
}

/* Position Section */
.position-section {
  background: linear-gradient(135deg, #4ecdc4 0%, #44a08d 100%);
  padding: 30px;
  border-radius: 20px;
  color: white;
}

.position-section .section-title {
  color: white;
  border-left-color: white;
}

.position-card {
  background: rgba(255, 255, 255, 0.2);
  padding: 30px;
  border-radius: 15px;
  backdrop-filter: blur(10px);
  text-align: center;
}

.position-title {
  font-size: 2.5rem;
  margin-bottom: 15px;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
  animation: titleBounce 2s ease-in-out infinite;
}

@keyframes titleBounce {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

.position-description {
  font-size: 1.1rem;
  line-height: 1.8;
  margin-bottom: 25px;
  text-align: justify;
}

.position-benefits {
  background: rgba(255, 255, 255, 0.15);
  padding: 20px;
  border-radius: 10px;
  margin: 25px 0;
  text-align: left;
}

.position-benefits h4 {
  font-size: 1.3rem;
  margin-bottom: 15px;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2);
}

.position-benefits ul {
  list-style: none;
  padding: 0;
}

.position-benefits li {
  font-size: 1rem;
  line-height: 1.8;
  margin-bottom: 10px;
  padding-left: 10px;
}

.position-closing {
  font-size: 1.1rem;
  line-height: 1.8;
  margin-top: 20px;
  font-style: italic;
  text-align: center;
}

/* Interviewer Section */
.interviewer-section {
  background: linear-gradient(135deg, #ffd93d 0%, #f6c23e 100%);
  padding: 30px;
  border-radius: 20px;
  text-align: center;
}

.interviewer-section .section-title {
  color: #333;
  border-left-color: #333;
}

.interviewer-card {
  background: white;
  padding: 30px;
  border-radius: 15px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
}

.interviewer-text {
  font-size: 1.1rem;
  color: #666;
  margin-bottom: 15px;
}

.interviewer-name {
  font-size: 2rem;
  color: #667eea;
  font-weight: bold;
  margin-bottom: 15px;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
}

.interviewer-badge {
  display: inline-block;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 10px 20px;
  border-radius: 20px;
  font-weight: 600;
  box-shadow: 0 5px 15px rgba(102, 126, 234, 0.3);
  margin: 20px 0;
}

.interviewer-details {
  margin-top: 20px;
  text-align: left;
}

.interviewer-details p {
  font-size: 1rem;
  line-height: 1.8;
  color: #555;
  margin-bottom: 15px;
  text-align: justify;
}

/* Footer */
.cv-footer {
  text-align: center;
  padding-top: 30px;
  margin-top: 40px;
  border-top: 3px solid #667eea;
}

.footer-text {
  font-size: 1.2rem;
  color: #667eea;
  font-style: italic;
  margin-bottom: 15px;
  font-weight: 600;
}

.footer-decoration {
  font-size: 2rem;
  animation: footerFloat 3s ease-in-out infinite;
}

@keyframes footerFloat {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}

/* Floating Elements */
.floating-elements {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 0;
}

.floating-icon {
  position: absolute;
  font-size: 3rem;
  opacity: 0.2;
  animation: floatAround 15s infinite ease-in-out;
}

.floating-icon:nth-child(1) {
  top: 10%;
  left: 5%;
  animation-delay: 0s;
}

.floating-icon:nth-child(2) {
  top: 30%;
  right: 10%;
  animation-delay: 3s;
}

.floating-icon:nth-child(3) {
  bottom: 30%;
  left: 8%;
  animation-delay: 6s;
}

.floating-icon:nth-child(4) {
  bottom: 10%;
  right: 5%;
  animation-delay: 9s;
}

@keyframes floatAround {
  0%,
  100% {
    transform: translate(0, 0) rotate(0deg);
  }
  25% {
    transform: translate(30px, -30px) rotate(90deg);
  }
  50% {
    transform: translate(-20px, -60px) rotate(180deg);
  }
  75% {
    transform: translate(-40px, -30px) rotate(270deg);
  }
}

/* Responsive */
@media (max-width: 768px) {
  .cv-content {
    padding: 20px;
  }

  .cv-name {
    font-size: 2rem;
  }

  .cv-photo {
    width: 150px;
    height: 150px;
  }

  .section-title {
    font-size: 1.4rem;
  }

  .big-zero {
    font-size: 5rem;
  }

  .position-title {
    font-size: 1.8rem;
  }

  .cv-intro {
    font-size: 0.9rem;
    padding: 15px;
  }

  .skill-name {
    font-size: 1rem;
  }

  .interest-item {
    flex-direction: column;
    text-align: center;
  }

  .interest-icon {
    font-size: 2rem;
  }
}
</style>
