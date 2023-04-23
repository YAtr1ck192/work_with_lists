<template>
    <div
        :class="[{'picked' : clearList.pick === true}, 'elem']"
        :id="clearList.id"
        @click="$emit('pickClearListItem', clearList)"
    >
        {{ clearList.itemName }}
    </div>
</template>

<script>

export default {
    name: "clearList",
    props: ['clearList'],
}
</script>

<style scoped>
.picked {
    background: rgba(63, 131, 154, 0.57);
}
.elem {
    padding: 55px 100px;
}
.listContent{
    border: solid 1px black;
}

</style>
