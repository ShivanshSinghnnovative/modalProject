<template>
    <div id="hideBox">
        <div class="MainDiv" @click.self="closeModal()">
            <div :class="['centerDiv', theme === 'buy' ? 'buy' : 'sell']">
                <h2 class='modalTitle'>{{ nameTitle }}</h2>
                <p class="modalContent">{{ content }}</p>
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'ModalBox',
    props: ['nameTitle', 'content', 'theme'],
    methods: {
        closeModal() {
            this.$emit('close');
        }
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

.sell {
    background-color: red;
    color: white;
}

.buy {
    background-color: green;
    color: black
}

.MainDiv {
    height: 100vh;
    width: 100vw;
    z-index: 10;
    position: fixed;
    top: 0;
    left: 0;
    background-color: rgb(0, 0, 0, 0.8);
    display: flex;
    justify-content: center;
    align-items: center;
}

.centerDiv {
    width: fit-content;
    border-radius: 0.5rem;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

.modalTitle {
    font-weight: 600;
    font-size: 33px;
    padding: 1.4rem 4rem;
}

.modalContent {
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

.slot {
    text-align: center;
    padding: 5px;
}

a {
    border: 1px solid black;
    text-decoration: none;
    padding: 5px;
    display: inline;
    border-radius: 2px;
    padding: 0.5rem 1rem;
    margin-left: auto;
    margin-right: auto;
    width: fit-content;
    justify-content: center;
    color: white;
    background-color: grey;
}

@media screen and (min-width:120px) and (max-width:600px) {
    .centerDiv {
        padding: .5rem;
        gap: 0.4rem;
    }

    .modalTitle {
        font-weight: 600;
        font-size: 18px;
        padding: .7rem 1rem;
    }

    .modalContent {
        font-size: 15px;
        padding-bottom: 1.3rem;
    }
}
</style>