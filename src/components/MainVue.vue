<template>
    <div class="container space-y-1 p-2">
        <h1>Greetings, courageous quest-seeker! Look upon the challenge that calls to you:</h1>
        <p class="" v-if="lockedQuest"> {{ quest }}</p>
        <input v-else @keypress.enter="lockQuest" v-model="quest" class="border-black rounded-md p-1 border-2 w-full"
            type="text">
        <p v-if="lockedQuest">Don't worry, brave one! The quest you picked is hard, but you can make it easier. Just break
            it into smaller
            parts using your smarts. Or, if you want, ask the wizard for help. He's here to make things simpler. You decide,
            and we'll face the challenge together!</p>
    </div>
</template>

<script setup>
    import { ref } from 'vue'
    const quest = ref('')
    const lockedQuest = ref(false)
    const lockQuest = () => {
        lockedQuest.value = true
    }
</script>