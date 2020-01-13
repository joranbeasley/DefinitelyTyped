<template>
  <div>
    <Draggable v-model="itemList" @start="startDrag" @end="endDrag">
      <div class="item" :key="itm" v-for="itm in itemList"> {{ itm }}</div>
    </Draggable>
  </div>
</template>
<script lang="ts">
import Vue from 'vue'
import Draggable from 'vuedraggable'
import { Component } from 'vue-property-decorator'

@Component({ components: { Draggable } })
export default class DemoSortable extends Vue {
        itemList: string[] = ['A', 'B', 'C', 'D', 'E']
        startDrag () {
          console.log('START DRAG:', this.itemList.join(', '))
        }
        endDrag () {
          console.log('END DRAG:', this.itemList.join(', '))
        }
}

</script>
<style scoped>
  div.item {
    padding: 50px;
    margin: 10px;
    font-weight: bolder;
    font-size: 20px;
    border: thin solid black
  }

  .sortable-chosen {
    border: #2c3e50 thick dashed !important;
  }

</style>
