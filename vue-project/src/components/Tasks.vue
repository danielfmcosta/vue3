<template>
    <div>
        <div :key="task.id" v-for="task in tasks">
            <TheTask @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task" />
        </div>
    </div>
</template>

<script>
    import TheTask from './Task.vue'

    export default {
        name: 'TheTasks',
        props: {
            tasks: Array 
        },
        components: {
            TheTask,
        },
        emits: ['delete-task', 'toggle-reminder'],
    }
</script>