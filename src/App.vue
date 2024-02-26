<script>
export default {
  data() {
    return {
      City: "",
      Error: ""
    };
  },
  methods: {
    getWeather() {
      if(this.City.trim().length < 2) {
        this.Error = "Enter a name containing more than 2 characters";
        return false;
      }
      else this.Error = "";
    }
  }
}
</script>

getWeather() {
if (this.City.trim().length < 2) {
Error = "Enter a name containing more than 2 characters";
return false;
}
else Error = "";
}
<template lang="pug">
  section.main
    .wrapper
      .wrapper-grid
        h1 Weather Today
        h2 Weather on {{City === "" ? "Your City" : City}}
        .wrapper-input-row
          label.wrapper-label City
          input.wrapper-input(type="text" v-model="City" placeholder="  Your City" maxlength="20")
        button.wrapper-button(v-show="City !== ''" @click="getWeather()" type="submit") Submit
        p.error-message(v-show="Error !== ''") {{Error}}
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
  border-radius: 70px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  h1 {
    color: white;
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
    grid-gap: 1vh;
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
    border: white solid 2px;
    border-radius: 30px;
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

  .error-message {
    color: white;
    font-style: italic;
  }
}
</style>
