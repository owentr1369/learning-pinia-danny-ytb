<template>
  <div class="home">
    <div class="count">{{ count }}</div>
    <div class="buttons">
      <button @click="decreaseCount">Decrease</button>
      <button @click="increaseCount">Increase</button>
    </div>
    <hr />
    <div>This counter is: {{ oddOrEven }}</div>
  </div>
</template>

<script setup>
import { computed, ref } from "vue";

const count = ref(1);

const decreaseCount = () => {
  count.value--;
};

const increaseCount = () => {
  count.value++;
};

const oddOrEven = computed(() => {
  if (count.value % 2 === 0) return "even";
  return "odd";
});
</script>


<style>
.count {
  font-size: 60px;
  margin: 20px;
}
.buttons button {
  font-size: 40px;
  margin: 10px;
  border-radius: 4px;
}
</style>
