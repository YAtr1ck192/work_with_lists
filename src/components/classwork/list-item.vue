<template>
    <div>
        <li>{{ student.name }}</li>
        <button @click="$emit('deleteItem', student)">удалить</button>
    </div>
</template>

<script>
export default {
    name: "listItem",
    props: ['student'],
    data () {
        return{
        }
    },
    methods: {

    }
}
</script>

<style scoped>

</style>