<template>
    <div class="container">
        <div class="output">
        <p class="text-success">{{cnvrtText}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'translatedText',
    props: {
        cnvrtText: {
            type: String,
            required: true
        }
    }
}
</script>

<style scoped>
    .output{
        margin: 22px;
        padding: 12px;
        font-size: 55px;
    }
</style>
