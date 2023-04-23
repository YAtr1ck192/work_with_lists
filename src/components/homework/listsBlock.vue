<template>
    <div class="block">
        <div class="fb">
            <listItem
                v-for="(item) in items"
                :key="item.id"
                :list="item"
                class="elem"
            />
        </div>

        <div class="buttons">
            <button
                class="onLeft"
                @click="onLeft()"
            >
                <img src="/img/arrow-on-left.png" alt="arrow">
            </button>
            <button
                class="onRight"
                @click="onRight()"
            >
                <img src="/img/arrow-on-left.png" alt="arrow">
            </button>
        </div>

        <div class="sb">
            <clearList
                v-for="(item) in itemsClearList"
                :key="item.id"
                :clearList="item"
                class="elem"
            />
            <clearList />
        </div>
    </div>
</template>

<script>
import clearList from "@/components/homework/clearList.vue";
import listItem from "@/components/homework/listItem.vue";

export default {
    name: "listsBlock",
    computed: {
    },
    data () {
        return {
            items: [
                {itemName: 'item1', id:'1', pick: false},
                {itemName: 'item2', id:'2', pick: false},
                {itemName: 'item3', id:'3', pick: false},
                {itemName: 'item4', id:'4', pick: false},
                {itemName: 'item5', id:'5', pick: false},
            ],
            itemsClearList: [
            ],
            index: '',
            i: '',
            count: 0,
        }
    },
    components: {
        clearList,
        listItem
    },
    methods: {
        onRight() {
            for (let j = 0; j <= this.count; j++){
                for (this.i = 0; this.i < this.items.length; this.i++){
                    if (this.items[this.i].pick === true) {
                        this.count++
                        this.addItem()
                        this.deleteItem()
                    }
                }
            }

        },
        addItem () {
            this.itemsClearList.push({itemName: this.items[this.i].itemName, id: this.items[this.i].id, pick: false})
        },
        deleteItem () {
            this.items.splice(this.i, 1)
        },
        onLeft () {
            for (let j = 0; j <= this.count; j++){
                for (this.i = 0; this.i < this.itemsClearList.length; this.i++){
                    if (this.itemsClearList[this.i].pick === true) {
                        this.count++
                        this.addItemLeft()
                        this.deleteItemLeft()
                    }
                }
            }
        },
        addItemLeft () {
            this.items.push({itemName: this.itemsClearList[this.i].itemName, id: this.itemsClearList[this.i].id, pick: false})
        },
        deleteItemLeft () {
            this.itemsClearList.splice(this.i, 1)
        },
    }
}
</script>

<style scoped>
.block {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 180px;
}
.onRight img {
    transform: rotate(180deg);
}
.buttons{
    display: flex;
    flex-direction: row;
    max-width: 320px;
    max-height: 150px;
}
button img{
    max-width: 150px;
    max-height: 150px;
    cursor: pointer;
}
.sb, .fb {
    border: solid 1px black;
    width: 240px;
    height: 640px;
}
.elem {
    padding: 55px 100px;
}
</style>
