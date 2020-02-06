<template>
    <ul>
        <li 
            v-for="photographer in photographers"
            v-bind:key="photographer">
            <input type="radio"
                v-on:change="$emit('radioOnPhotographer', photographer.id)"
                v-bind:id="photographer.id"
                v-bind:value="photographer.id"
                name="photographers">
            <label v-bind:for="photographer.id">{{photographer.name}}</label>
        </li>
    </ul>
</template>

<script>
export default {
    props: ['photographers']
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
</style>