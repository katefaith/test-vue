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
        flex-basis: 38%;
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
        font-size: 23px;
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
</style>