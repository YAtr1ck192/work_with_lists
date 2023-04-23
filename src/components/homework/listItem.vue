<template>
    <div
        :class="[{'picked' : list.pick === true}, 'elem']"
        :id="list.id"
        @click="$emit('pickItem', list)"
    >
        {{ list.itemName }}
    </div>
</template>

<script>
export default {
    name: "listItem",
    props: ['list'],
    methods: {

    }
}
</script>
<style scoped>
.picked {
    background: rgba(63, 131, 154, 0.57);
}

.listContent{
    border: solid 1px black;
}
</style>
