<script setup lang="ts">
import { ref } from 'vue'
import ListItem from './components/ListItem.vue'

const listItems = ref([
  {
    name: 'Anastasia V',
    image: false,
    lvl: 1,
  },
  {
    name: 'Anastasia V',
    image: false,
    lvl: 1,
  },
  {
    name: 'Dmitro',
    image: false,
    lvl: 1,
  },
  {
    name: 'Diana',
    image: false,
    lvl: 15,
  },
  {
    name: 'Nikita',
    image: false,
    lvl: 99,
  },
  {
    name: 'Nikita',
    image: false,
    lvl: 99,
  },
  {
    name: 'Nikita',
    image: false,
    lvl: 99,
    isChampion: true,
  },
  {
    name: 'Nikita',
    image: false,
    lvl: 99,
    isChampion: true,
  },
  {
    name: 'Nikita',
    image: false,
    lvl: 99,
    isChampion: true,
  },
])
</script>

<template>
  <section class="body">
    <div class="header">
      <h1 class="header__main">invite friends!</h1>
      <span class="header__sub">You and your friend will receive bonuses!</span>
    </div>

    <div class="links">
      <div class="links__link links__image_1">
        <div class="links__buttons">
          <button type="button" class="button button_yellow">more bonuses</button>
        </div>
      </div>

      <div class="links__link links__image_2">
        <div class="links__buttons">
          <button type="button" class="button button_blue">invite</button>

          <button type="button" class="button button_blue">
            <div class="button__image button__image_link"></div>
          </button>
        </div>
      </div>
    </div>

    <div class="list">
      <p class="list__text">List of your friends</p>

      <button type="button" class="button button_yellow button_main">
        Claim
        <div class="button__image button__image_currency"></div>
        12.5k
      </button>

      <div class="list__items">
        <ul class="list__inner">
          <ListItem v-for="(item, index) in listItems" :item :key="index" />
        </ul>
      </div>
    </div>
  </section>
</template>

<style scoped lang="scss">
.body {
  min-height: 100vh;
  background: radial-gradient(51.09% 70.69% at 50% 52.89%, #3081b4 0%, #19488c 100%);
  padding: 23px 7px 13px;
}

.header {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-bottom: 12px;
}

.header__main {
  text-shadow:
    -0.5px -0.5px 0 black,
    0.5px -0.5px 0 black,
    0 2px 0 black,
    0.5px 0.5px 0 black;

  font-family: 'Movavi', sans-serif;
  font-weight: 900;
  font-size: 24px;
  text-transform: uppercase;
  text-align: center;
  color: #facb46;
}

.header__sub {
  @include text;
  font-size: 14px;
  font-weight: 600;
}

.links {
  display: flex;
  justify-content: space-between;
  gap: 10px;
  margin-bottom: 12px;
}

.links__link {
  border: 2px solid #7dd0ff;
  border-radius: 12px;
  max-width: 160px;
  width: 100%;
  height: 115px;
  display: flex;

  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

.links__image_1 {
  background-image: url('./assets/images/Frame\ 2131329026.png');
}

.links__image_2 {
  background-image: url('./assets/images/Frame\ 2131329169.png');
}

.links__buttons {
  display: flex;
  justify-content: center;
  gap: 16px;
  width: 100%;
  padding: 5px;
  backdrop-filter: blur(1px);
  align-self: end;
}

.button {
  @include text;
  @include button;

  max-width: 80%;
}

.button_yellow {
  @include mainButton(#f7cb40);
}

.button_blue {
  @include mainButton(#44a2e5);
}

.button__image {
  background-position: center;
  background-repeat: no-repeat;
  width: 100%;
  height: 100%;
}

.button__image_link {
  background-image: url('./assets/images/Icons\ 16х16.svg');
}

.button__image_currency {
  background-image: url('./assets/images/dsaddasdas\ 5.svg');
  height: 12px;
  width: 12px;
  margin: 0 4px 0 8px;
}

.button_main {
  font-size: 14px;
  line-height: 143%;
  max-width: 142px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.list {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  gap: 8px;
}

.list__text {
  @include text;
  font-weight: 900;
  font-size: 16px;
}

.list__items {
  border-radius: 12px;
  width: 100%;
  box-shadow: inset 0 4px 4px 0 rgba(0, 3, 6, 0.5);
  background: radial-gradient(51.09% 70.69% at 50% 52.89%, #3081b4 0%, #19488c 100%);
  padding: 10px 4px;
}

.list__inner {
  width: 100%;

  max-height: 440px;
  overflow: hidden;
  overflow-y: scroll;

  gap: 8px;
  display: flex;
  flex-direction: column;
}
</style>
