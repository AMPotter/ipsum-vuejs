<template>
    <div class="hello">
        <h1>The Ipsum List</h1>
        <ul>
            <li
                v-for="ipsum in ipsums"
                v-bind:key="ipsum.title"
                v-bind:class="{ selected: selected === ipsum }"
                v-on:click="$emit('selected', ipsum)"
            >
                {{ipsum.title}}
            </li>
        </ul>
    </div>
</template>

<script>
import ipsums from '../data/ipsums';

export default {
    data() {
        return { ipsums };
    },
    props: ['selected']
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
    margin: 40px 0 0;
}
ul {
    list-style-type: none;
    padding: 0;
}
li {
    display: inline-block;
    margin: 0 10px;
    cursor: pointer
}

li.selected {
    background: #aaa;
}
</style>