<template>
    <div>
        <article v-if="ipsum">
            <h2>{{ipsum.title}}</h2>
            <p>
                Posted on {{ipsum.publishedOn}} in {{ipsum.category}}
                by <a :href="ipsum.authorUrl">{{ipsum.author}}</a>
            </p>
            <div v-html="ipsum.body"></div>
        </article>
        <p v-else>Please select an ipsum</p>
    </div>
</template>

<script>
export default {
    data: { foo: 'foo' },
    props: ['ipsum']
};
</script>

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
}
</style>
