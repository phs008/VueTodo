<template>
    <div class="inputBox shadow">
        <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo" placeholder="Type what you have to do">
        <span class="addContainer" v-on:click="addTodo">
            <i class="addBtn fa fa-plus" aria-hidden="true">
            </i>
        </span>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newTodoItem: ''
        }
    },
    methods : {
        clearInput()
        {
            this.newTodoItem = "";
        },
        addTodo(){
            if(this.newTodoItem != "")
            {
                let value = this.newTodoItem && this.newTodoItem.trim();
                this.$emit('addTodo',value);
                this.clearInput();
            }
        }
    }
}
</script>

<style scoped>
    input:focus {
        outline: none;
    }
    .inputBox{
        background: white;
        height: 50px;
        line-height: 50px;
        border-radius: 5px;
    }
    .inputBox input{
        border-style: none;
        font-size: 0.9rem;
    }
    .addContainer{
        float: right;
        background: linear-gradient(to right, #6478FB,#8763FB);
        display: inline-block;
        width: 3rem;
        border-radius: 0 5px 5px 0
    }
    .addBtn{
        color: white;
        vertical-align: middle;
    }
</style>
