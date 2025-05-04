<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>To-Do List</title>
  <style>
    body {
  font-family: Arial, sans-serif;
  background-color: #f0f4f8;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.todo-container {
  background-color: white;
  padding: 2rem;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

input {
  padding: 10px;
  font-size: 1rem;
  width: 200px;
}

button {
  padding: 10px 15px;
  margin-left: 10px;
  font-size: 1rem;
  cursor: pointer;
}

ul {
  list-style: none;
  padding: 0;
  margin-top: 20px;
}

li {
  padding: 10px;
  background-color: #e0f7fa;
  margin-bottom: 10px;
  border-radius: 5px;
  display: flex;
  justify-content: space-between;
}

li.completed {
  text-decoration: line-through;
  color: gray;
}
  </style>
</head>
<body>
  <div class="todo-container">
    <h1>To-Do List</h1>
    <input type="text" id="taskInput" placeholder="Add a new task" />
    <button onclick="addTask()">Add</button>
    <ul id="taskList"></ul>
  </div>
  <script>
    function addTask() {
  const taskInput = document.getElementById("taskInput");
  const taskList = document.getElementById("taskList");
  const taskText = taskInput.value.trim();

  if (taskText === "") return;

  const li = document.createElement("li");
  li.textContent = taskText;

  // Toggle complete
  li.addEventListener("click", () => {
    li.classList.toggle("completed");
  });

  // Delete on double click
  li.addEventListener("dblclick", () => {
    li.remove();
  });

  taskList.appendChild(li);
  taskInput.value = "";
}
  </script>
</body>
</html>
