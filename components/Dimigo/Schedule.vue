<script setup lang="ts">

</script>

<template>
  <div class="scheduleContainer">
    <h1>Schedule</h1>
    <div class="box">
      <table>
        <tr>
          <th>월</th>
          <th>화</th>
          <th>수</th>
          <th>목</th>
          <th>금</th>
        </tr>
        <tr>
          <td>플밍</td>
          <td>플밍</td>
          <td>체육</td>
          <td>진로</td>
          <td>컴일</td>
        </tr>

        <tr>
          <td>사물</td>
          <td>과학</td>
          <td>컴일</td>
          <td>플밍</td>
          <td>사회</td>
        </tr>

        <tr>
          <td>영어</td>
          <td>체육</td>
          <td>사회</td>
          <td>영어</td>
          <td>사물</td>
        </tr>

        <tr>
          <td>음악</td>
          <td>진로</td>
          <td>국어</td>
          <td>사물</td>
          <td>음악</td>
        </tr>

        <tr>
          <td>컴일</td>
          <td>영어</td>
          <td>수학</td>
          <td>수학</td>
          <td>플밍</td>
        </tr>

        <tr>
          <td>수학</td>
          <td>국어</td>
          <td>CA</td>
          <td>과학</td>
          <td>국어</td>
        </tr>
        <tr>
          <td>HR</td>
          <td>음악</td>
          <td/>
          <td>사회</td>
          <td>과학</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<style scoped>
.scheduleContainer {
  width: 30rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 2rem;
}

.box {
  width: 100%;
  padding: 2rem;
  background-color: var(--box-color);
  border-radius: 1rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

table {
  width: 100%;
}

th, td {
  text-align: center;
  padding: 0.8rem;
  font-size: 1.2rem;
  color: var(--text-color);
}
</style>
