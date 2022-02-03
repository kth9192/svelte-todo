<script>
    import ToDo from './components/toDo.svelte';
    import Input from './components/input.svelte';

    let todo = '';
    let todoList = [
        {
            id: 1,
            text: '할일이',
            completed: false,
        },
        {
            id: 2,
            text: '너무많다',
            completed: false,
        },
        {
            id: 3,
            text: '살려줘',
            completed: true,
        },
    ];

    let lastId = todoList[todoList.length - 1]['id'];

    let addTodo = () => {
        if (todo) {
            let newTodo = {
                id: ++lastId,
                text: todo,
                completed: false,
            };

            todoList[todoList.length] = newTodo;
            todo = '';
        }
    };

    let handleKeyPress = (e) => {
        todo = e.target.value;
        if (e.keyCode === 13) {
            addTodo();
        }
    };

    let deleteTodo = (id) => {
        todoList = todoList.filter((todo) => todo.id !== id);
    };

    let handleComplete = (id) => {
        const index = todoList.findIndex((todo) => todo.id === id);
        todoList[index]['completed'] = !todoList[index]['completed'];
    };
</script>

<div class="cover">
    <h1>To Do List</h1>
    <Input {todo} {addTodo} {handleKeyPress} />
    <ToDo {todoList} {deleteTodo} {handleComplete} />
</div>

<style lang="scss">
    .cover {
        display: flex;
        width: 40vw;
        height: 50vh;
        flex-direction: column;
        padding: 20px;
        box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
    }
</style>
