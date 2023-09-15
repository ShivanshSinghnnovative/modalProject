<template>
  <div class="container">
    <div class="contentBox">
      <button @click="openModal" id="modelButton">Show Modal</button>
      <ModalS v-if="isModalVisible" nameTitle="Sign up for the Giveaway!" content="Grab your ninja swag for half Price"
        theme="sell" @close="closeModal">
        <template #links>
          <a>Google</a>
          <a>Facebook</a>
        </template>
      </ModalS>

      <input ref="myInput" type="text" id="input" />
      <button @click="focusInput()" id="focusButton">Focus</button>
    </div>
  </div>
</template>

<script>
import ModalS from './components/ModalS.vue'
export default {
  name: 'App',
  components: {
    ModalS
  },

  data() {
    return {
      isModalVisible: false,
    };
  },
  methods: {
    openModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    },
    focusInput() {
      this.$refs.myInput.focus();
    }
  }

}
</script>

<style >
.container {
  position: relative;
  width: 100%;
  height: 100vh;
}

button {
  background: #1d3027;
  color: white;
  border-radius: .2rem;
  cursor: pointer;

}

.contentBox {
  border: 2px solid black;
  background-color: rgb(40, 82, 82);
  box-shadow: 5px 7px #dfdede;
  margin-left: auto;
  margin-right: auto;
  width: fit-content;
  margin-top: 10%;
  padding: 5rem;
  gap: 1rem;

}

#input {
  display: block;
  height: .8rem;
  padding: .5rem;
  width: 12rem;
}

#focusButton {
  padding: .5rem;
  margin-left: auto;
  margin-right: auto;
  display: block;
  text-align: center;
  margin-top: 1rem;
}
</style>
