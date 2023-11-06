<script setup lang="ts"></script>

<template>
  <div id="about" class="aboutContainer">
    <h1>About me</h1>
    <div class="content">
      <img class="profileImg" src="/assets/images/about/profile.jpeg"/>
      <div class="careerBox">
        <div id="dimipay" class="section">
          <div class="title">
            <h2>DIMIPAY</h2>
            <hr/>
            <h3>23.10~</h3>
          </div>
          <ul>
            <li>
              <p>배우ㄱing</p>
            </li>
          </ul>
        </div>
        <div id="kdmhs" class="section">
          <div class="title">
            <h2>KDMHS</h2>
            <hr/>
            <h3>23.03~</h3>
          </div>
          <ul>
            <li>
              <p><strong>제 5회 한국코드페어 해커톤 금상 👑 (SNNECT)</strong></p>
            </li>
            <li>
              <p>Junction Aisa 2023 본선 진출 (TasteByYou)</p>
            </li>
            <li>
              <p>STAC 2023 결선 진출 (Glud)</p>
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
  padding: 6rem 0;
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
}

.careerBox {
  width: 100%;
  border-radius: 1rem;
  background-color: white;
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

#dimipay hr {
  width: 100%;
  height: 0.25rem;
  background-color: #2EA4AB;
  border: 0.1rem solid #2EA4AB;
  border-radius: 0.2rem;
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
</style>
