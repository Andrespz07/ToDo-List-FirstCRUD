<script setup>
import { reactive } from 'vue'

const crearNombre = reactive({
  nombres: [
  ],
  nuevoNombre: '',
  nombreEditada: '',
  indexNombreEditada: -1
})

const agregarNombre = () => {
  if (crearNombre.nuevoNombre !== '') {
    crearNombre.nombres.push({
      titulo: crearNombre.nuevoNombre
    })
    crearNombre.nuevoNombre = ''
  }
}

const editarNombre = (index) => {
  crearNombre.nombreEditada = crearNombre.nombres[index].titulo
  crearNombre.indexNombreEditada = index
}

const guardarCambios = () => {
  if (crearNombre.indexNombreEditada !== -1) {
    crearNombre.nombres[crearNombre.indexNombreEditada].titulo = crearNombre.nombreEditada
    crearNombre.nombreEditada = ''
    crearNombre.indexNombreEditada = -1
  }
}

const eliminarNombre = (index) => {
  crearNombre.nombres.splice(index, 1)
}
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
              id="inputNombre"
              placeholder="Enter your name"
              v-model="crearNombre.nuevoNombre"
              v-on:keyup.enter="agregarNombre"
            /> 
            <button type="button" class="btn btn-primary" id="addToDo" @click="agregarNombre">
              send
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
              v-model="crearNombre.nombreEditada"
              v-on:keyup.enter="guardarCambios"
            />
            <button type="button" class="btn btn-primary" id="addToDo" @click="guardarCambios">
              edit
            </button>
          </div>
        </div>
      </div>
  
      <section class="task-list">
        <div id="tasks">
          <table class="table">
            <thead>
              <tr>
                <th scope="col">Names</th>
                <th scope="col"></th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(nombre, index) in crearNombre.nombres" :key="index">
                <th scope="row">{{ nombre.titulo }}</th>
                <td>
                  <div class="actions">
                    <button class="edit btn btn-success fa-solid fa-pen-to-square" type="button" @click="editarNombre(index)"></button>
                    <button class="delete btn btn-danger fa fa-trash" @click="eliminarNombre(index)"></button>
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
