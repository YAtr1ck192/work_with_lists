<template>
    <div
        :class="[{'picked' : clearList.pick === true}, 'elem']"
        :id="clearList.id"
        @click="pickItem(clearList.pick)"
    >
        {{ clearList.itemName }}
    </div>
</template>

<script>

export default {
    name: "clearList",
    data () {
        return{
            pick: false
        }
    },
    props: ['clearList'],
    methods: {
        pickItem () {
            // eslint-disable-next-line vue/no-mutating-props
            this.clearList.pick = !this.clearList.pick
        },
    }
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
