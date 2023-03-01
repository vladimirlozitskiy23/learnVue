<template>
<ul>
    <!-- здесь обязательно использовать key, чтобы использовать и перемещать элементы
    если бы мы получали данные из базы данных то использовали бы поле id -->
    <li v-for="(todo,index) in todos" @click="deleteTodo(index)" :key="index">{{ todo }}</li>
</ul>
</template>

<script>
    export default {
        //чтобы получить данные используем свойство props,если бы мы использовали в App.vue кебаб кейс
        // todos-list например в атрибутах,то здесь нужно было бы писать в кэмэл кейс ["todosList"]
        props: ['todos'],
        methods: {
            deleteTodo(index){
                this.$emit("delete-todo",index);
            }
        }
    }  

</script>