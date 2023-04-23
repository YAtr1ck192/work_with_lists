<template>
    <div
        :class="[{'picked' : list.pick === true}, 'elem']"
        :id="list.id"
        @click="pickItem(list.pick)"
    >
        {{ list.itemName }}
    </div>
</template>

<script>
export default {
    name: "listItem",
    props: ['list'],
    methods: {
        pickItem () {
            // eslint-disable-next-line vue/no-mutating-props
            this.list.pick = !this.list.pick
        },
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
