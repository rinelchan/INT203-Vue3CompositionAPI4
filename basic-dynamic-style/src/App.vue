<script setup>
import { reactive, ref, computed } from "vue";
const cardList = reactive([]);
for (let i = 0; i < 12; i++) {
  cardList.push({
    value: i,
    visible: false,
    position: i,
    matched: false
  });
}

const shuffleCard = () => {
  cardList.value = _.shuffle(cardList.value)
}

const restart = () => {
  shuffleCard()

  cardList.value = cardList.value.map(card => {
    return {
      ...card,
      matched: false,
      position: index,
      visible: false
    }
  })
}



// true = แดง / false = น้ำเงิน ได้แหละ
// const visible = {
//   type: Boolean,
//   default: false,
// };

const flipCard = (index) => {
  cardList[index].visible = true;
};
</script>
<template>
  <section class="game-board">
    <div
      class="card"
      v-for="(card, index) in cardList"
      :key="`card-${index}`"
      :value="card.value"
      :visible="card.visible"
      :position="card.position"
      @click="flipCard(index)"
    >
      <div v-if="cardList[index].visible" class="card-face is-front">
        {{ index }}
      </div>
      <div v-else class="card-face is-back">Back</div>
    </div>
  </section>



<button @click="restart">RESTART GAME</button>

</template>

<style>
.card {
  border: 5px solid#ccc;
  position: relative;
}
.card-face {
  width: 100%;
  height: 100%;
  position: absolute;
}

.card-face.is-front {
  background-color: red;
  color: white;
}
.card-face.is-black {
  background-color: blue;
  color: white;
}
.game-board {
  display: grid;
  grid-template-columns: 100px 100px 100px 100px;
  grid-template-rows: 100px 100px 100px 100px;
  grid-column-gap: 30px;
  grid-row-gap: 30px;
  justify-content: center;
}
</style>



