<template>
    <section class="container">
        <h1>{{ title }}</h1>
        <p>{{ message }}</p>

        <table>
            <tr>
                <th>User ID</th>
                <td>{{ json_data.userID }}</td>
            </tr>
            <tr>
                <th>ID</th>
                <td>{{ json_data.id }}</td>
            </tr>
            <tr>
                <th>Title</th>
                <td>{{ json_data.title }}</td>
            </tr>
            <tr>
                <th>Body</th>
                <td>{{ json_data.body }}</td>
            </tr>
        </table>
    </section>
</template>

<script>
const axios = require('axios');

let url = "https://jsonplaceholder.typicode.com/todos/";

export default {
    data: function() {
        return{
            title: 'Axios',
            msg: '',
            message: 'axios sample'
        };
    },

    async asyncData() {
        let id = 1;
        let result = await axios.get(url + id);
        return{
            json_data: result.data
        };
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
    tr th {
        width: 150px;
        background: darkblue;
        color: white;
        font-size: 1rem;
    }
    tr td {
        padding: 5px 10px;
        background: #eef;
        font-size: 1rem;
    }
</style>
