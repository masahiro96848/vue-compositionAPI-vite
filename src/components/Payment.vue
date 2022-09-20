<script setup lang="ts">
    const itemName1 = 'Desk'
    const itemName2 = 'Bike'

    const price1 = 40000
    const price2 = 20000

    const url1 = 'https://yutaro-blog.net/2022/03/04/freelance-web-engineer-2/#index_id11'
    const buy = (itemName: string) => {
        alert('購入しますか？' + itemName + '?')
    }

    const input = (event: any) => {
        console.log('ddddd', event.target.value)
    }
</script>

<template>
    <div class="container">
        <h1>最近の支出</h1>
        <div class="payment">
            <input v-on:input="input">
            <label for="">{{ itemName1 }}</label>
            <label for="">{{ price1 }}</label>
            <a v-bind:href="url1">bought at</a>
            <button v-on:click="buy(itemName1)">Buy</button>
        </div>
        <div class="payment">
            <label for="">{{ itemName2 }}</label>
            <label for="">{{ price2 }}</label>
        </div>
    </div>
</template>

<style scoped>
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.payment {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 80px;
    width: 400px;
    background-color: aliceblue;
}

label {
    font-size: 20px;
}
</style>