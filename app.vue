<template>
  <div class="wrapper" ref="wrapper">
    <i class="fas fa-heart"></i>
    <h2 ref="question">Do you love me?</h2>
    <div class="btn-group">
      <button @click="handleYes">Yes</button>
      <button class="no-btn" @mouseover="handleNo">No</button>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    this.wrapper = this.$refs.wrapper;
    this.question = this.$refs.question;
    this.noBtn = this.$el.querySelector('.no-btn');
  },
  methods: {
    handleYes() {
      this.question.innerHTML = 'I Love You Too';
    },
    handleNo() {
      const wrapperRect = this.wrapper.getBoundingClientRect();
      const noBtnRect = this.noBtn.getBoundingClientRect();
      const i = Math.floor(Math.random() * (wrapperRect.width - noBtnRect.width)) + 1;
      const j = Math.floor(Math.random() * (wrapperRect.height - noBtnRect.height)) + 1;
      this.noBtn.style.left = i + 'px';
      this.noBtn.style.top = j + 'px';
    }
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@600;700&display=swap');

* {
  color: #ca0606;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-image: url(love2.webp);
  background-size: cover;
}

.wrapper {
  position: relative;
  width: 27rem;
  height: 25rem;
  backdrop-filter: blur(7px);
  background: rgba(255, 255, 255, 0.2);
  border-radius: 14px;
  box-shadow: 10px 12px 10px black;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

i {
  padding: 1.4rem;
  font-size: 7.5em;
  color: rgb(218, 12, 12);
  border-radius: 50%;
}

h2 i {
  font-size: 1.1em;
  color: #3c0ce6;
  margin: 15px 0;
}

.btn-group {
  padding: 1.2rem;
  width: 100%;
  height: 40px;
  display: flex;
  justify-content: center;
  margin-top: 15px;
}

button {
  width: 130px;
  height: inherit;
  font-size: 1.2em;
  color: #fff;
  font-weight: 600;
  border-radius: 30px;
  border: 2px solid #e1dce7;
  outline: none;
  cursor: pointer;
  box-shadow: 0 2px 4px rgba(0, 0, 0, .3);
  position: relative;
}

button:hover {
  box-shadow: 6px 4px 20px rgb(247, 248, 246);
}

button:nth-child(1) {
  margin-left: -200px;
  background: #7d2ae8;
}

button:nth-child(2) {
  margin-right: -200px;
  color: #e10707;
}

.no-btn {
  color: rgb(15, 9, 2);
}
</style>
