# actividades
pequeños proyectos de estudio
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lista de Tareas</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        #task-list {
            list-style-type: none;
            padding: 0;
        }
        .task {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border: 20px solid #ddd;
            padding: 20px;
            margin: 5px 0;
        }
        .task.completed {
            text-decoration: line-through;
            color: #999;
        }
        button {
            background-color: blue;
            color: white;
            border: none;
            cursor: pointer;
        }
        .delete-button {
    background-color: red;
    color: white;
    border: none;
    cursor: pointer;
}

    </style>
</head>
<body>
    <h1><u>Lista de Tareas</u></h1>
    <input type="text" id="task-input" placeholder="Agregar una nueva tarea">
    <button onclick="addTask()">Agregar</button>
    <ul id="task-list"></ul>

    <script>
        const taskList = document.getElementById("task-list");
        const taskInput = document.getElementById("task-input");

        function addTask() {
            const taskText = taskInput.value.trim();
            if (taskText !== "") {
                const taskItem = document.createElement("li");
                taskItem.classList.add("task");
                taskItem.innerHTML = `
                    <span>${taskText}</span>
                    <button onclick="completeTask(this)">Completar</button>
                    <button onclick="deleteTask(this)" class="delete-button">Eliminar</button>
                `;
                taskList.appendChild(taskItem);
                taskInput.value = "";
            }
        }

        function completeTask(button) {
            const taskItem = button.parentElement;
            taskItem.classList.toggle("completed");
        }

        function deleteTask(button) {
            const taskItem = button.parentElement;
            taskList.removeChild(taskItem);
        }
    </script>
</body>
</html>

