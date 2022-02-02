<script>
  export let todo
  export let deleteTodo
  export let handleComplete 
</script>

<style lang="scss">
.check{
  margin:0;
}

.listItem{
display:flex;
align-items:center;
gap:10px;
}

.delete{
  background:transparent;
  border:none;
  cursor:pointer;
  color:#5942bd;
}

.checked{
  text-decoration:line-through
}

</style>

<li class="listItem">
<input type="checkbox" class="check" checked={todo.completed} on:change={()=>handleComplete(todo.id)}/>
<p  class:checked={todo.completed}>{todo.text}</p>
  <button class="delete" on:click={() => deleteTodo(todo.id)}>x</button>
</li>