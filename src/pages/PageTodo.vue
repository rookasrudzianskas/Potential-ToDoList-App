<template>
  <q-page class="q-pa-md">
    <q-list
      separator
      bordered>
     <q-item v-for="task in tasks" :key="task.id"  :class="!task.completed ? 'bg-orange-1' : 'bg-green-1'" @click="task.completed = !task.completed" clickable v-ripple>
       <q-item-section side top>
         <q-checkbox v-model="task.completed" />
       </q-item-section>

       <q-item-section>
         <q-item-label
         :class="{ 'text-strikethrough' : task.completed }"
         >{{ task.name }}</q-item-label>
       </q-item-section>
       <q-item-section side>
         <div class="row">
           <div class="column justify-center">
         <q-icon
           name="event"
           size="18px"
           class="q-mr-xs"
         />
           </div>
           <div class="column">
         <q-item-label
           class="row justify-end"
           caption>
         {{ task.dueDate }}
         </q-item-label>

         <q-item-label
           class="row justify-end"
           caption>
           <small>{{ task.dueTime }}</small>
         </q-item-label>
           </div>
         </div>
       </q-item-section>

     </q-item>
    </q-list>
  </q-page>
</template>

<script>
// import Task from 'components/Task'
export default {
  data() {
    return {
      tasks: [
        {
          id: 1,
          name: 'Go to shop',
          completed: false,
          dueTime: '14:30',
          dueDate: '2020/05/12',
        },
        {
          id: 2,
          name: 'Go to home',
          completed: false,
          dueTime: '14:30',
          dueDate: '2020/05/15',
        },
        {
          id: 3,
          name: 'Go to school',
          completed: false,
          dueTime: '14:30',
          dueDate: '2020/05/14',
        },
      ]
    }
  }
}
</script>

<style>

</style>
