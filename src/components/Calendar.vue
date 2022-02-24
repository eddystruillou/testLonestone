<template>
  <div class="button">
    <button @click="previousMonth">previous</button>
    <button @click="nextMonth">next</button>
  </div>
  <div class="calendar">
    <div class="calendarTitle">
      <h2>May 2018</h2>
    </div>
    <div class="calendar__date">
      <div class="calendar__day">M</div>
      <div class="calendar__day">T</div>
      <div class="calendar__day">W</div>
      <div class="calendar__day">T</div>
      <div class="calendar__day">F</div>
      <div class="calendar__day">S</div>
      <div class="calendar__day">S</div>
      <div class="calendar__number"></div>
      <div class="calendar__number"></div>
      <div class="calendar__number"></div>
      <div v-for="number in arrayNumber" v-bind:key="number">
        {{ number }}
      </div>
    </div>
  </div>
</template>

<script>
import { onMounted } from '@vue/runtime-core';
import {ref} from 'vue';

export default {
  name: "Calendar",
  setup() {
    let arrayNumber = ref([]);
    let month = ref(1);

    const nextMonth = function () {
      month.value++;
      updateMonth();
    }

    const updateMonth = function () {
      let nbDay = new Date(2022, month.value + 1, 0).getDate();
      arrayNumber.value = [];
      for (let i = 1; i <= nbDay; i++) {
        arrayNumber.value.push(i);
      }
    }

    onMounted(() => {
      updateMonth();
    });

    return {
      arrayNumber,
      nextMonth
    }
  }
}
</script>

<style scoped>
.calendar {
  position: relative;
  width: 300px;
  background-color: #fff;
  box-sizing: border-box;
  box-shadow: 0 5px 50px rgba(#000, 0.5);
  border-radius: 8px;
  overflow: hidden;
}

.calendar__date {
  padding: 20px;
  display: grid;
  grid-template-columns: repeat(7, minmax(25px, 1fr));
  grid-gap: 10px;
  box-sizing: border-box;
}

.calendar__day {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 25px;
  font-weight: 600;
  color: #262626;
}

.calendar__number {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 25px;
  color: #262626;
}
</style>
