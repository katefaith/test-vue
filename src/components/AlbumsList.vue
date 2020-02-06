<template>
    <ul>
        <li 
            v-for="album in albums"
            v-bind:key="album">
            <input type="radio"
                v-on:change="$emit('radioOnAlbum', album.id)"
                v-bind:id="album.id"
                v-bind:value="album.id"
                name="albums">
            <label v-bind:for="album.id">{{album.title}}</label>
        </li>
    </ul>
</template>

<script>
export default {
    props: ['albums']
}
</script>

<style scoped>
    ul {
        flex-basis: 59%;
        margin: 5px 10px;
        padding: 0;
        list-style: none;
    }

    li {
        display: flex;
        margin-bottom: 3px;
        background-color: #fff;
    }

    label {
        flex-basis: 100%;
        padding: 3px 5px;
        cursor: pointer;
    }

    input[type=radio]:checked + label {
        background-color: #e0e0e0;
    }

    input[type=radio] + label:hover {
        background-color: #e0e0e0;
    }

    input[type=radio] {
        display: none;
    }
</style>>