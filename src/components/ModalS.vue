<template>
    <div id="hideBox">
        <div class="MainDiv" v-on:click="hideModel()">
        </div>

        <div class="centerDiv">
            <h2 class="modalTitle">{{ nameTitle }}</h2>
            <p class="modalContent">{{ name }}</p>
            <slot name="links" class="slot"></slot>
        </div>
    </div>
    <button id="modelButton" v-on:click="openData()">ShowModal</button>
</template>
<script>
export default {
    name: 'ModalS',
    props: ['nameTitle', 'name'],
    methods: {
        openData() {
            document.getElementById('hideBox').style.display = "block";
            document.getElementById('modelButton').style.display = "none";
        },
        hideModel() {
            document.getElementById('hideBox').style.display = "none";
            document.getElementById('modelButton').style.display = "flex";
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

#hideBox {
    display: none;
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