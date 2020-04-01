<template>
    <div id="app">
        <Header />
        <AddTodo v-on:add-todo="addTodo" />
        <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
    </div>
</template>

<script>
import axios from 'axios';

import Header from './components/layouts/Header';
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';

export default {
    name: 'App',
    components: { Header, Todos, AddTodo },
    data() {
        return {
            todos: []
        };
    },
    methods: {
        deleteTodo(id) {
            axios
                .delete(`http://jsonplaceholder.typicode.com/todos/${id}`)
                // eslint-disable-next-line no-unused-vars
                .then(res => (this.todos = this.todos.filter(todo => todo.id !== id)))
                .catch(err => console.log(err));
        },
        addTodo(newTodo) {
            const { title, completed } = newTodo;

            axios
                .post('http://jsonplaceholder.typicode.com/todos', {
                    title,
                    completed
                })
                .then(res => (this.todos = [...this.todos, res.data]))
                .catch(err => console.log(err));
        }
    },
    created() {
        axios
            .get('http://jsonplaceholder.typicode.com/todos?_limit=5')
            .then(res => (this.todos = res.data))
            .catch(err => console.log(err));
    }
};
</script>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
}
</style>
