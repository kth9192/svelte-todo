<script>
    import TodoItem from "./todoItem.svelte"
    export let todoList
    export let deleteTodo
    export let handleComplete 
</script>

<style>
.todoList{
    display:flex;
    flex-direction:column;
    padding:0;
}
</style>

<ul class="todoList">
    {#each todoList as todo}
        <TodoItem {todo} {deleteTodo} handleComplete />
    {/each}
</ul>