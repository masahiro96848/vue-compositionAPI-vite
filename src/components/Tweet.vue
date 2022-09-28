<script setup lang="ts">
import { ref } from 'vue'
import TweetPostForm from './TweetPostForm.vue';
import TweetList from './TweetList.vue';

const tweets = ref( [{ id: 0, description: 'Hello World'}, { id: 1, description: 'This is a pen'}])

const inputtingDescription = ref<string>()
const postTweet = (description: string) => {
    const tweet  = { id: Math.random(), description}
    tweets.value.push(tweet)
}

const deleteTweet = (id: number) => {
    tweets.value = tweets.value.filter(t => t.id !== id )
}

</script>

<template>
    <div class="container">
        <h1>Tweeter</h1>
        <TweetPostForm @post-tweet="postTweet" />
        <div class="tweet-container">
            <p v-if="tweets.length <= 0">No tweets have been added</p>
            <ul>
                <TweetList @delete-tweet="deleteTweet" :tweets="tweets"/>
            </ul>
        </div>
    </div>
</template>

<style scoped>
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.form-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: aliceblue;
    padding: 24px 0;
    width: 60%;
    margin-bottom: 12px;
    border-radius: 4px;
}


</style>