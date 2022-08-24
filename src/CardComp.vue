<template>
  <div>
    <img :src="item.image" class="room-img" />
    <h4 @click="send">
      {{ item.title }}
    </h4>
    <p>{{ item.price }}원</p>
  </div>
</template>
<script>
export default {
  name: "CardComp",
  props: {
    item: Object,
    i: Number,
  },
  components: {},
  data() {
    return {
      sampleData: "",
    };
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    send() {
      this.$emit("openModal", this.item.id);
    },
  },
};
</script>
