<template>
  <div class="body">
    <h1 class="title">Color Checker</h1>
    <div class="container">
      <div class="square">
        <span class="text" :style="{ fontSize: fontSize + 'px' }">
          This is a
          <span v-if="showColorInput && isValidColor">{{ bgColorInput }}</span>
          <span v-else>{{ prevValidBgColor }}</span>
          <!-- Menampilkan nilai sebelumnya jika input tidak valid -->
          color
        </span>
        >
      </div>
      <div class="square square2" ref="secondSquare"></div>
    </div>

    <div class="form-container">
      <div class="input-container">
        <input
          type="text"
          v-model="fontSizeInput"
          @input="changeFontSize"
          placeholder="Enter size... (px)"
        />
        <button @click="increaseFontSize">Increase (+)</button>
        <button @click="decreaseFontSize">Decrease (-)</button>
        <p>Font size : {{ fontSizeInput }} px</p>
      </div>
      <div class="input-container">
        <input
          type="text"
          v-model="bgColorInput"
          placeholder="Enter color... (name/hex)"
        />
        <button @click="changeBackgroundColor">View Color</button>
        <p>Color : {{ bgColorInput }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, watch } from "vue";

const fontSize = ref(16);
const fontSizeInput = ref("");
const bgColorInput = ref("");
const secondSquare = ref(null);
const isValidColor = ref(true);
const showColorInput = ref(false);

const changeFontSize = () => {
  fontSize.value = parseInt(fontSizeInput.value) || 16;
};

const increaseFontSize = () => {
  fontSize.value++;
};

const decreaseFontSize = () => {
  if (fontSize.value > 1) {
    fontSize.value--;
  }
};

let prevValidBgColor = "";

const changeBackgroundColor = () => {
  const dummyDiv = document.createElement("div");
  dummyDiv.style.backgroundColor = bgColorInput.value;
  if (dummyDiv.style.backgroundColor) {
    isValidColor.value = true;
    showColorInput.value = true;
    if (secondSquare.value) {
      secondSquare.value.style.backgroundColor = bgColorInput.value;
      showAlert();
    }
    prevValidBgColor = bgColorInput.value;
  } else {
    isValidColor.value = false;
    showColorInput.value = false;
    alert("Sorry, the color is not available, please try another one.");
    bgColorInput.value = prevValidBgColor;
  }
};
const showAlert = () => {
  alert("Yohoo, the color is available!");
};
</script>

<style scoped>
.body {
  margin-top: -1rem;
  height: 100vh;
  background-image: url(../../public/bg.jpeg);
  background-size: cover;
}
.title {
  color: #000;
  font-size: 3rem;
  text-align: center;
  text-shadow: 4px 2px 19px rgb(0, 248, 243);
}

.container {
  display: flex;
  align-items: center;
  justify-content: center;
}

.square {
  width: 400px;
  height: 400px;
  border-radius: 40px;
  position: relative;
  margin: 15px;
  background-color: white;
}
span {
  font-weight: bolder;
}
.text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  max-width: calc(100% - 20px);
  max-height: calc(100% - 20px);
  overflow: hidden;
  white-space: nowrap;
  font-weight: bold;
}

.form-container {
  height: 100px;
  margin-top: 20px;
  display: flex;
  justify-content: center;
}

.input-container {
  margin-right: 50px;
  flex-shrink: 0;
}
.input-container input {
  padding: 8px 8px;
  border-radius: 5px;
  font-size: 0.8rem;
  font-weight: bold;
}

.input-container button {
  margin-left: 5px;
  padding: 8px 8px;
  border-radius: 5px;
  font-size: 0.8rem;
  font-weight: bold;
}

input[type="text"],
button {
  justify-content: space-around;
}

button {
  background-color: #6f94bc;
  color: #fff;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

input[type="text"]::placeholder {
  color: #999;
}

h1,
p {
  font-size: 1.6rem;
  margin-top: 1rem;
  line-height: 1.4;
  font-weight: bolder;
  text-shadow: 4px 2px 15px rgb(0, 255, 68);
}

@media screen and (max-width: 768px) {
  .container {
    flex-direction: column;
  }

  .square {
    width: 200px;
    height: 200px;
  }

  .text {
    max-width: calc(100% - 10px);
    max-height: calc(100% - 10px);
  }

  .form-container {
    flex-direction: column;
  }

  .input-container {
    margin-right: 0;
    margin-bottom: 20px;
  }
}
</style>
