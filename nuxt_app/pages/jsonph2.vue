<template>
    <section class="container">
        <h1>{{ title }}</h1>
        <p>{{ message }}</p>
        <div>
            <input type="text" v-model="msg">
            <button @click="doClick">Click</button>
        </div>
        <hr>
        <table>
            <tr>
                <th>User ID</th>
                <td>{{ json_data.userId }}</td>
            </tr>
            <tr>
                <th>ID</th>
                <td>{{ json_data.id }}</td>
            </tr>
            <tr>
                <th>Title</th>
                <td>{{ json_data.title }}</td>
            </tr>
            <!-- <tr>
                <th>Completed</th>
                <td>{{ json_date.completed }}</td>
            </tr> -->
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
            json_data: {}
        };
    },
    methods: {
        doClick: function(event) {
            axios.get(url + this.msg).then((res) => {
                this.message = 'get ID=' + this.msg;
                this.json_data = res.data;
            }).catch((error) =>{
                this.message = 'ERROR!';
                this.json_data = {};
            });
        },
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
        font-size: 1rem;
    }
    div {
        font-size: 1rem;
    }
    hr {
        margin: 20px 0;
        border-top: 1px solid #ccc;
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