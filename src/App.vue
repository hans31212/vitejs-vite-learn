<script setup>
// This starter template is using Vue 3 <script setup> SFCs
import todo from './components/todoItem.vue'


function todoItem(done=false, content='', children=[]) {
  return {
    "done" : done,
    "content" : content,
    "children" : children
  }
}

const todoList = [
  todoItem(false, 'Create todoApp', [
    todoItem(true, 'Setup environment', [
      todoItem(true, 'Install Vue'),
      todoItem(true, 'Install Tailwind')
    ]),
    todoItem(false, 'Create TodoItem Component')
  ])
]
</script>
<template>
  <div 
  class="flex flex-col w-full items-center p-4"
  >
    <todo 
    v-for="item in todoList"
    :key="(Math.random().toString(36).substring(2))"
    :todo="item"
    />
  </div>
</template>