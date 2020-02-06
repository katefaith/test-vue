<template>
    <ul>
        <li 
            v-for="picture in pictures"
            v-bind:key="picture">
            <img 
                v-bind:src="picture.thumbnailUrl" 
                v-bind:alt="picture.title"
                width="150" height="150">
        </li>
    </ul>
</template>

<script>
export default {
    props: ['pictures']
}
</script>

<style scoped>
    ul {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        margin: 0;
        padding: 0;
        list-style: none;
    }

    li {
        margin-bottom: 10px;
    }

    img {
        display: block;
    }
</style>