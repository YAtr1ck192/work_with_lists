<template>
    <ul>
        <ListItem
            v-for="(item, index) in items"
            :key="index"
            :student="item"
            @deleteItem="deleteItem(index)"
        />
        <input type="text" v-model="newStudent">
        <button @click="addItem">добавить</button>
    </ul>
</template>

<script>
import ListItem from "@/components/classwork/list-item.vue";
export default {
    name: "listBlock",
    components: {ListItem},
    data () {
      return {
          newStudent: '',
          i:5,
          items:[
              {name:'tolya', id:'1'},
              {name:'sasha', id:'2'},
              {name:'slava', id:'3'},
              {name:'sasha', id:'4'},
          ]
      }
    },
    methods: {
        addItem () {
            this.items.push({name: this.newStudent, id: this.i})
            this.i++
        },
        deleteItem (index) {
            // console.log(item)
            // const index = this.items.findIndex((a) => {
            //     return a.id === item.id
            // })
            // console.log(index)
            this.items.splice(index, 1)
        }

    }
}
</script>

<style scoped>

</style>