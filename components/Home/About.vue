<script setup lang="ts">
</script>

<template>
  <div id="about" class="aboutContainer">
    <h1>About me</h1>
    <div class="content">
      <img class="profileImg" src="/images/about/profile.jpeg" />
      <div class="careerBox">
        <div id="kdmhs" class="section">
          <div class="title">
            <h2>KDMHS</h2>
            <hr />
            <h3>23.03~</h3>
          </div>
          <ul>
            <li>
              <p>IT 소셜벤처 동아리 LUNA (23.12~)</p>
            </li>
            <li>
              <p><strong>STA+C 2023 SK플래닛대표상 👑 (23.11)</strong></p>
            </li>
            <li>
              <p><strong>제5회 한국코드페어 해커톤 과학기술정보통신부장관상 👑 (23.11)</strong></p>
            </li>
            <li>
              <p>디미고 교내 무인매점 결제 솔루션 개발팀 디미페이 (23.10~)</p>
            </li>
            <li>
              <p>Junction Aisa 2023 본선 진출 (23.08)</p>
            </li>
            <li>
              <p>디미고 22기 학생홍보팀 (23.03~)</p>
            </li>
            <li>
              <p>정보보안 동아리 Stealth, STARE (23.03~23.12)</p>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.aboutContainer {
  width: 100%;
  display: flex;
  align-items: center;
  flex-direction: column;
  gap: 2rem;
  padding: 8rem 0;
}

.content {
  display: flex;
  flex-direction: row;
  gap: 1rem;
  width: 100%;
}

.profileImg {
  max-height: 25rem;
  border-radius: 1rem;
  object-fit: cover;
  object-position: center;
}

.careerBox {
  width: 100%;
  border-radius: 1rem;
  background-color: var(--box-color);
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  padding: 2rem 1.5rem;
}

.title {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 1rem;
}

#kdmhs hr {
  width: 100%;
  height: 0.25rem;
  background-color: deeppink;
  border: 0.1rem solid deeppink;
  border-radius: 0.2rem;
}

.section {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.section ul {
  margin-left: 1.5rem;
}

.section li {
  height: 2.5rem;
}

@media (max-width: 768px) {
  .aboutContainer {
    padding: 5rem 1rem;
    gap: 2rem 1rem;
  }

  .profileImg {
    max-height: 12rem;
    border-radius: 0.5rem;
  }

  .content {
    flex-direction: column;
    gap: 0.5rem;
  }

  .careerBox {
    padding: 1rem;
    gap: 0.5rem;
    border-radius: 0.5rem;
  }

  .title {
    gap: 0.5rem;
  }

  .section ul {
    margin-left: 1rem;
  }

  .section li {
    height: 2rem;
  }
}
</style>
