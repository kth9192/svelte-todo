<script>
    export let todo;
    export let addTodo;
    export let handleKeyPress;
</script>

<div>
    <input
        class="inputTxt"
        type="text"
        placeholder="할일을 입력하세요"
        bind:value={todo}
        on:keypress={(e) => handleKeyPress(e)}
    />
    <button class="sumbit" on:click={addTodo}>ADD</button>
</div>

<style>
    .inputTxt {
        border: none;
        border-radius: 5px;
        box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
    }

    .sumbit {
        background-color: #5942bd;
        color: white;
        border-radius: 5px;
    }
</style>
