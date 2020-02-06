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
        margin: 0;
        margin-bottom: 20px;
        padding: 0;
        list-style: none;
    }

    input[type=radio]:checked + label {
        color: blue;
    }

    input[type=radio] + label:hover {
        color: blue;
    }

    input[type=radio] {
        display: none;
    }
</style>>