<template>
    <section class="container">
        <h1>{{ title }}</h1>
        <p>{{ message }}</p>
        <pre>{{ html_data }}</pre>
    </section>
</template>

<script>
const axios = require('axios');

let url = "/README.md";

export default {
    data: function() {
        return {
            title: 'Axios',
            message: 'axios sample'
        };
    },
    asyncData: async function() {
        let result = await axios.get(url);
        return { html_data: result.data };
    },
}
</script>

<style>
    .container {
        padding: 5px 10px;
    }
    h1 {
        font-size: 10rem;
        color: #345980;
    }
    p {
        padding-top: 5px;
        font-size: 3rem;
    }
    div {
        font-size: 1rem;
    }
    pre {
        padding: 10px;
        font-size: 1.2rem;
        background: #efefef;
        white-space: pre-wrap;
    }
    ht {
        margin-top: 10px 0;
    }
</style>