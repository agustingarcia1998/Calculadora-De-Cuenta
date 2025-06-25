<script setup>
import { ref } from 'vue';
import { store, calculate } from '@/store/store';

const total = ref(0);
const tip = ref(0);
const people = ref(0);

function handleSubmit(){
    store.params.total = total;
    store.params.tip = tip;
    store.params.people = people;
    calculate();

}


</script>


<template>
<form action="" @submit.prevent="handleSubmit">
    <div class="form-container">
        <div>
            <label for="total">Total</label>
            <input type="number" required v-model="total"/>
        </div>

        <div>
            <label for="tip">Tip %</label>
            <input type="number" required v-model="tip">
        </div>

        <div>
            <label for="people">People</label>
            <input type="number" required v-model="people">
        </div>

        <div>
             <input type="submit" value="Calculate"/>   
        </div>

    </div>
</form>
</template>


<style scoped>
form{
    width: 400px;
    background-color: rgb(23, 129, 78);
    height: 100vh;
    display: flex;
    align-items: center;
    color: white;
    font-size: 18px;
    padding: 20px;
}

.form-container{
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 20px;
}

form label{
    display: block;
}

form input{
padding: 10px;
width: 100%;
box-sizing: border-box;
font-size: 18px;
}
</style>