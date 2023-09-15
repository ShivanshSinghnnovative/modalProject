<template>
    <div id="hideBox">
        <div class="MainDiv" v-on:click="closeModal()"></div>

        <div :class="['centerDiv', theme]">
            <h2 :class="['modalTitle', theme]">{{ nameTitle }}</h2>
            <p class="modalContent">{{ content }}</p>
            <slot name="links"></slot>
        </div>
    </div>
</template>
<script>
export default {
    name: 'ModalS',
    props: ['nameTitle', 'content', 'theme'],
    methods: {
        closeModal() {
            this.$emit('close');
        },

    }
}


</script>
<style  >
* {
    margin: 0;
    padding: 0;
    font-family: sans-serif;
    overflow-x: hidden;
    overflow-y: hidden;
}

.centerDiv.sell {
    background-color: red;
    color: white;
}

.centerDiv.buy {
    background-color: green;
    color: rgb(0, 0, 0);
}
.modalTitle.buy{
    color: black;
}

#hideBox {

    margin: 0;
    padding: 0;
}

.MainDiv {
    height: 100vh;
    width: 100vw;
    z-index: 10;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 1;
    background-color: rgb(0, 0, 0, 0.2);
}

.slot {
    text-align: center;
    padding: 5px;
}

a {
    border: 1px solid black;
    text-decoration: none !important;
    padding: 5px;
    display: inline;
    border-radius: 2px;
    padding: 0.5rem 1rem;
    margin-left: auto;
    margin-right: auto;
    width: fit-content;
    justify-content: center;
    align-items: center;
    text-align: center;
    color: white;
    background-color: grey;
}

.centerDiv {
    width: fit-content;
    margin-right: auto;
    position: absolute;
    z-index: 10;
    border-radius: 0.5rem;

    left: 35%;
    top: 30%;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    gap: 1rem;
    background-color: rgb(186, 46, 46);
}

.modalTitle {
    color: white;
    font-weight: 600;
    font-size: 33px;
    padding: 1.4rem 4rem;
}

.modalContent {
    color: white;
    text-align: center;
    padding-bottom: 1.3rem;
}

#modelButton {
    padding: .5rem;
    display: block;
    margin-left: auto;
    margin-right: auto;
    margin-bottom: 1rem;
}
</style>