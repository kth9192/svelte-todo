<script>
  export let todo;
  export let addTodo;
  export let handleKeyUp;
</script>

<style>
.sumbit{
    background-color:#5942BD;
    color:white;
    border-radius:5px;
}
</style>

<div>
  <input type="text" placeholder="할일을 입력하세요" bind:value={todo} on:keyup={e => handleKeyUp(e)}/>
  <button class="sumbit" on:click={addTodo}>ADD</button>
</div>