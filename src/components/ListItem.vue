<template>
  <li class="item">
    <div class="item__block">
      <img v-if="item.image" :src="item.image.src" :alt="item.name" />

      <div v-else class="item__photo"></div>
    </div>

    <p class="item__text">{{ item.name }}</p>

    <div class="item__lvl">
      <div v-if="item.isChampion" class="item__medal"></div>
      <p class="item__text">{{ item.lvl }} lvl</p>
    </div>
  </li>
</template>

<script setup lang="ts">
const props = defineProps(['item'])
</script>

<style scoped lang="scss">
.item {
  width: 100%;
  padding: 6px 4px;
  background: radial-gradient(51.09% 70.69% at 50% 52.89%, #3081b4 0%, #19488c 100%);

  display: flex;
  align-items: center;
  gap: 8px;

  position: relative;
}

.item::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 1px;
  background: linear-gradient(
    to right,
    rgba(0, 0, 0, 0.2) 0%,
    rgba(255, 255, 255, 0.5) 50%,
    rgba(0, 0, 0, 0.2) 100%
  );
}

.item__photo {
  border-radius: 4px;
  width: 30px;
  height: 30px;
  box-shadow: 0 1px 4px 0 rgba(0, 174, 229, 0.5);
  background-color: #15376c;

  background-image: url('../assets/images/icon\ Question.png');
  background-position: center;
  background-repeat: no-repeat;
  background-size: 20px;
}

.item__text {
  @include text;
  font-size: 10px;
  font-weight: 900;
}

.item__lvl {
  margin-left: auto;
  width: 100%;
  max-width: 72px;

  display: flex;
  align-items: center;
  gap: 4px;
}

.item__medal {
  background-image: url('../assets/images/Union.svg');
  background-position: center;
  background-repeat: no-repeat;
  background-size: 20px;

  width: 27px;
  height: 25px;
}
</style>
