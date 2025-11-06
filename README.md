<!DOCTYPE html>
<html lang="en"> 
<head> 
  <meta charset="UTF-8"> 
  <title>Simple To-Do List</title> 
  <style> 
    body { 
      font-family: Arial, sans-serif; 
      max-width: 400px; 
      margin: 40px auto; 
    } 
 
    h2 { 
      text-align: center; 
    } 
 
    #taskInput { 
      width: 75%; 
      padding: 10px; 
      font-size: 16px; 
    } 
 
    #addBtn { 
      padding: 10px 16px; 
      font-size: 16px; 
    } 
 
    ul { 
      list-style-type: none; 
      padding: 0; 
    } 
 
    li { 
      margin: 10px 0; 
      padding: 10px; 
      background-color: #f2f2f2; 
      display: flex; 
      justify-content: space-between; 
      align-items: center;  
    } 
 
    .removeBtn { 
      background-color: red; 
      color: white; 
      border: none; 
      padding: 6px 10px; 
      cursor: pointer; 
    } 
 
    .removeBtn:hover { 
      background-color: darkred; 
    } 
  </style> 
</head> 
<body> 
 
  <h2>To-Do List</h2> 
 
  <!-- Input and Add Button --> 
  <input type="text" id="taskInput" placeholder="Enter a task"> 
  <button id="addBtn" onclick="addTask()">Add</button> 
 
  <!-- Task List --> 
  <ul id="taskList"></ul> 
 
  <script> 
    function addTask() { 
      const input = document.getElementById("taskInput"); 
      const taskText = input.value.trim(); 
 
      if (taskText === "") { 
        alert("Please enter a task."); 
        return; 
      } 
 
      // Create list item 
      const li = document.createElement("li"); 
      li.textContent = taskText; 
 
      // Create remove button 
      const removeBtn = document.createElement("button"); 
      removeBtn.textContent = "Remove"; 
      removeBtn.className = "removeBtn";  
      removeBtn.onclick = function () { 
        li.remove(); // Remove the task when button is clicked 
      }; 
 
      // Append button to list item 
      li.appendChild(removeBtn); 
 
      // Append list item to task list 
      document.getElementById("taskList").appendChild(li); 
 
      // Clear input 
      input.value = ""; 
    } 
  </script> 
 
</body> 
</html>
