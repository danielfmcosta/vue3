<template>
    <header>
        <h1>
            {{ title}}
        </h1>
        <AddButton 
            v-show="homePage"
            @btn-click="$emit('toggle-add-task')" 
            :text="showAddTask ? 'Close' : 'Add Task'" 
            :color="showAddTask ? 'red' : 'green'" 
        />

    </header>
</template>

<script>
import AddButton from './Button.vue'

export default {
    name: 'TheHeader',
    props: {
        title: String,
        showAddTask: Boolean,
    },
    components: {
        AddButton
    },
    computed: {
        homePage() {
            if(this.$router.path === '/'){
                return false;
            } else {
                return true;
                
            }
        }
    }
}
</script>

<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-content: center;
        margin-bottom: 20px;
    }
</style>