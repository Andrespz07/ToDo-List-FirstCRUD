<script setup>
// data:{
//     titulo: 'CRUD con Vue',

// }
</script>

<template>
  <div class="container">
    <header id="main-header" class="bg-dark text-white p-4 mb-3">
      <div class="row">
        <div class="col-md-12">
          <h1 id="header-title">To-Do List</h1>
        </div>
      </div>
    </header>

    <div class="card">
      <div class="card-body">
        <div class="input-group mb-3">
          <input
            type="text"
            class="form-control"
            id="inputField"
            placeholder="Enter item to do"
          />
          <button type="button" class="btn btn-primary" id="addToDo">
            <i class="fa fa-add"></i>
          </button>
        </div>
      </div>

      <div class="card-body">
        <div class="input-group mb-3">
          <input
            type="text"
            class="form-control"
            id="inputField"
            placeholder="Edit item"
          />
          <button type="button" class="btn btn-primary" id="addToDo">
            <i class="fa-solid fa-check"></i>
          </button>
        </div>
      </div>
    </div>

    <section class="task-list">
      <div id="tasks">
        <table class="table">
          <thead>
            <tr>
              <th scope="col">Task</th>
              <th scope="col"></th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <th scope="row">new task</th>
              <td>
                <div class="actions">
                  <button
                    class="edit btn btn-success fa-solid fa-pen-to-square"
                    type="button"
                  ></button>
                  <button class="delete btn btn-danger fa fa-trash"></button>
                </div>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </section>
  </div>
</template>

<style lang="scss" scoped></style>
