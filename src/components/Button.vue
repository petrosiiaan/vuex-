<template>
    <div class="button">
        <button class="button-btn">
            {{text}}
        </button>
    </div>
</template>


<script>
export default {
    props: {
        text: {
            type: String,
            default: "Submit Data"
        }
    }
}
</script>


<style scoped>
    .button {
        margin-right: 65px;
        margin-top: 20px;
    }
    .button-btn {
        padding: 10px;
        border: 0;
        background: cadetblue;
        font-size: 16px;
        color: white;
        cursor: pointer;
        outline: 0;
    }
</style>