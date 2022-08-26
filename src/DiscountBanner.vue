<template>
  <div class="discount">
    <h4>지금 결제하면 {{ discountPer }}% 할인</h4>
  </div>
</template>

<script>
export default {
  name: "DiscountBanner",
  data() {
    return {
      discountPer: 30,
    };
  },
  mounted() {
    setInterval(() => {
      if (this.discountPer > 0) {
        this.discountPer += -1;
      }
    }, 1000);
  },
};
</script>

<style></style>
