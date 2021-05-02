<template>
    <div :key="task.id" v-for="task in tasks">
        <Task @delete-task="$emit('delete-task', task.id)" @reminder-change="$emit('reminder-change', task.id)" :task= "task" />
    </div>
</template>

<script>
import Task from './Task'
export default {
    name: "Tasks",
    props:{
        tasks: Array,
    },
    components: {
        Task,
    },
    emits: ['delete-task', 'reminder-change']
}
</script>
