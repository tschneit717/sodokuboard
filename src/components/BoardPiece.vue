<script lang="ts">
    interface InputEvent extends Event {
        data: string;
    }
    export default {
        data() {
            return {
                value: 0
            }
        },
        methods: {
            inputChange(payload: InputEvent) {
                console.log(payload)
                const oldValue = this.value
                const number = parseInt(payload.data ?? '')
                if (!isNaN(number)) {
                    this.value = number
                } else {
                    this.value = oldValue
                    return 
                }
            }
        }
        
    }
</script>

<template>
    <input
        @input="inputChange"
        v-model="value"/>
</template>

<style scoped>
    button {
        font-weight: bold;
    }
</style>