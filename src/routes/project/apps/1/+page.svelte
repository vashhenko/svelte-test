<script>
    function remove(index) {
    todoList.splice(index, 1);
    todoList = todoList;
    }
    function complete(index) {
    todoListindex.completed = ItodoListindex.completed;
    }
    import Icon from '../../../../components/Icon.svelte';
    let newItem = '';
    let todoList = [];
    function add() {
    if (newItem !=='') {
        todoList = [
            ...todoList,
            {
        task: newItem,
        completed: false,
            }
    ];
    newItem = '';
        }
    }
    </script>
    
    <h1>Заметки</h1>
    <main>
        <form on:submit|preventDefault={add}>
        <input bind:value={newItem} placeholder="Напишите заметку..." />
        <button class="add-todo" on:click={add}>
        </button>
    </form>
    <div class="todos">
        {#each todoList as item, index}
        <div class="todo" class:completed={item.completed}>
        <span class="todo__text">{item.task}</span>
        <div class="todo__buttons">
            <button class="complete" on:click={()=> complete(index)}>
            <Icon name="check-mark" />
            </button>
            <button class="delete" on:click={() => remove(index)}>
            <Icon name="delete" />
            </button>
            </div>
            </div>
        {/each}
    </div>
    </main>
<style>
    .todos {
    width: 100%;
    max-width: 500px;
    }
    button {
    background-color: transparent;
    border: none;
    }
    button.delete,
    button.delete:hover {
    color: brown;
    transition: color 100ms ease-out;
    }
    button.complete,
    button.complete:hover {
    color: cadetblue;
    transition: color 100ms ease-out;
    }
    .todo.completed {
    color: slategray;
    }
    .todo.completed .todo__text {
        text-decoration: line-through;
    }
    .todo.completed button {
        color: silver;
    }
    .todo {
    display: flex;
    padding: 20px;
    border-radius: 20px;
    box-shadow: 0 0 15px rgb(0 0 0 / 20%);
    background-color: white (0, 0%, 100%, 0.2);
    margin-top: 1rem;
    font-size: 1.2rem;
    justify-content: space-between;
    align-items: center;
    }
    .todo__buttons {
    display: flex;
    align-items:center;
    margin-left: 1rem;
    }
    .todo button {
    width: 32px;
    height: 32px;
    padding: 4px;
    margin: 0;
    flex-shrink: 0;
    }
    h1 {
    text-align: center;
    font-size: 1.5rem;
    margin: 2em 0;
    }
    main{
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100%;
    padding: 5vmin;
    box-sizing: border-box;
    background: antiquewhite;
        }
    form {
    width: 100%;
    max-width: 500px;
    display: flex;
    align-items: center;
    margin-bottom: 1rem;
    }
    input {
    flex-grow: 1;
    width: 0;
    border: none;
    border-bottom: 1px solid black;
    background: transparent;
    box-shadow: none;
    font-size: 1.2rem;
    margin: 0;
    outline: none;
    }
    </style>