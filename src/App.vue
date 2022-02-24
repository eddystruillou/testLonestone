<template>
  <h1 class="title">Schedule Response</h1>
  <Date class="date" />
  <Time class="time" />
  <Calendar class="calendar" />
  <MultipleList class="multipleList" />
  <NavBar class="navBar" />
</template>

<script>
import Date from './components/Date.vue';
import Time from "./components/Time";
import Calendar from "./components/Calendar";
import MultipleList from "./components/MultipleList";
import NavBar from "./components/NavBar";

export default {
  name: 'App',
  components: {
    Date,
    Time,
    Calendar,
    MultipleList,
    NavBar
  }
}
</script>

<style>
#app {
  display: flex;
  flex-wrap: wrap;
  width: 50%;
  height: 50%;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  border: solid black 2px;
}

.title {
  width: 100%;
  text-align: left;
}

.date {
  width: 50%;
}

.time {
  width: 50%;
}

.calendar {
  width: 70%;
}

.multipleList {
  width: 30%;
}
</style>
