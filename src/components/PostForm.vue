<template>
    <div>
        <input type="text" placeholder="Title" v-model="title">
        <input type="text" placeholder="Body" v-model="body" @keypress.enter="submit">
        <Button text="Submit Data" @click="submit" />
    </div>
</template>

<script>
import Button from './Button'
import {mapMutations} from 'vuex'
export default {
    data() {
        return {
            title: "",
            body: ""
        }
    },
    components: {
        Button
    },
    methods: {
        ...mapMutations(['createPost']),
        submit(){
            if(!this.title || !this.body) {
                alert("Empty Field")
                return;
            }
            this.createPost({
                title: this.title,
                body: this.body,
                id: Date.now().toString()
            })

            this.title = '',
            this.body = ''
        }
    }
}
</script>

<style scoped>
    input {
        width: 50%;
        display: block;
        border-radius: 2px;
        border: 1px solid #ccc;
        margin-top: 10px;
        padding: 10px;
        outline: 0;
        font-size: 14px;
    }
</style>