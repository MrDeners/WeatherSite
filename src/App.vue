<script>
export default {
  data() {
    return {
      City: ""
    };
  }
}
</script>

<template lang="pug">
  section.main
    .wrapper
      .wrapper-grid
        span
          h1 Weather Today
          h2(v-if="City === ''") Weather on Your City
          h2(v-else) Weather on {{ City }}
        .wrapper-input-row
          label.wrapper-label City
          input.wrapper-input(type="text" v-model="City" placeholder="Your City")
        button.wrapper-button(type="submit") Submit

</template>

<style scoped lang="scss">
.main {
  height: 100vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.wrapper {
  background-color: #c91c45;
  height: 50vh;
  width: 60%;
  border: white solid 5px;
  border-radius: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  h1 {
    color: #e8dcdf;
    font-size: 40px;
  }

  h2 {
    color: white;
    font-size: 30px;
  }

  .wrapper-grid {
    height: 100%;
    width: 100%;
    display: grid;
    grid-gap: 3vh;
    justify-items: center;
    align-items: center;
  }

  .wrapper-input-row {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .wrapper-label {
    font-size: 20px;
    color: white;

    &::after {
      content: "";
    }
  }

  .wrapper-input {
    height: 5vh;
    width: 60%;
  }

  .wrapper-button {
    color: white;
    font-size: 20px;
    height: 5vh;
    width: 20%;
    background-color: #282828;
    border: white solid 2px;
    border-radius: 10px;
  }
}
</style>
