<script>
    export let todo;
    export let deleteTodo;
    export let handleComplete;
</script>

<li class="listItem">
    <input type="checkbox" class="check" checked={todo.completed} on:change={() => handleComplete(todo.id)} />
    <p class={`sentence ${todo.completed ? 'checked' : ''}`}>{todo.text}</p>
    <button class="delete" on:click={() => deleteTodo(todo.id)}>x</button>
</li>

<style lang="scss">
    .sentence {
        font-size: 18px;
    }

    .check {
        margin: 0;
    }

    .listItem {
        display: flex;
        align-items: center;
        gap: 10px;
    }

    .delete {
        background: transparent;
        border: none;
        cursor: pointer;
        color: #5942bd;
    }

    .checked {
        text-decoration: line-through;
    }
</style>
