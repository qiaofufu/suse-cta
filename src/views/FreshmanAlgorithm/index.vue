<script setup>
import ScoreRank from './components/scoreRank.vue';
import Introduction from './components/introduction.vue';
import { isRunningActive } from '@/api/activeTime.js'
import { ref } from 'vue';

const submit = () => {

}
const enable = ref(false)
isRunningActive('newborn_algorithm_competition').then(res => {
    enable.value = res.data.data
})
</script>
<template>
    <div id="algo-container">
        <ScoreRank id="algo-rank-container"></ScoreRank>
        <div id="algo-other-container">
            <Introduction></Introduction>
        </div>

    </div>
</template>
<style>
#algo-rank-container {
    width: 65%;
}

#algo-container {
    display: flex;
    justify-content: center;
}

#algo-other-container {
    width: 30%;
    margin-left: 20px;
}

#algo-btn {
    width: 100%;
    height: 55px;
    margin-top: 10px;
    font-size: 40px;
    background-color: #449D44;
    color: white;
}
</style>