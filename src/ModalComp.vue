<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img class="modalImg" :src="원룸들[누른거].image" />
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
      <!-- <input @input="month = $event.target.value" /> -->
      <input v-model.number="month" />
      <!-- <textarea v-model="month"></textarea> -->
      <select v-model="month">
        <option value="1">1</option>
        <option value="2">2</option>
        <option value="3">3</option>
        <option value="4">4</option>
      </select>
      <input type="range" min="1" max="12" v-model="month" />
      <p>{{ month }}개월 선택함 : {{ 원룸들[누른거].price * month }}원</p>
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalComp",
  data() {
    return {
      month: 1,
    };
  },
  watch: {
    month(a) {
      if (isNaN(a)) {
        alert("문자입력하지마셈");
        this.month = 1;
      }
    },
  },
  props: {
    원룸들: Object,
    누른거: Number,
    모달창열렸니: Boolean,
  },
};
</script>

<style></style>
