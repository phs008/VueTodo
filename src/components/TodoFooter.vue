<template>
    <div class="clearAllContainer">
        <div class="innerDiv">
            <span class="clearAllBtn" @click="clearTodo()">Clear All</span>
        </div>
    </div>
</template>

<script>
export default{
    methods:{
        clearTodo()
        {
            this.$emit('clearAllItems');
        }
    }
}
</script>

<style>
    .clearAllContainer{
        width: 8.5rem;
        height: 50px;
        line-height: 50px;
        background-color: white;
        border-radius: 5px;
        margin: 0 auto;
    }
    .clearAllBtn{
        color: #e20303;
        display: inline-block;
        cursor: default;
        border: 1px;
        border-color: black;
    }
</style>