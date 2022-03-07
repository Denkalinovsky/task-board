<template>
  <div class="table-row">
    <el-row>
      <el-col :span="6">
        <h3>Todo</h3>
        <draggable
          class="list-group"
          :list="list1"
          group="people"
          @change="log"
        >
          <div
            class="list-group-item"
            v-for="(element, index) in list1"
            :key="element.name"
          >
            {{ element.name }} {{ index }}
          </div>
        </draggable>
      </el-col>

      <el-col :span="6">
        <h3>Working</h3>
        <draggable
          class="list-group"
          :list="list2"
          group="people"
          @change="log"
        >
          <div
            class="list-group-item"
            v-for="(element, index) in list2"
            :key="element.name"
          >
            {{ element.name }} {{ index }}
          </div>
        </draggable>
      </el-col>

      <el-col :span="6">
        <h3>Done</h3>
        <draggable
          class="list-group"
          :list="list3"
          group="people"
          @change="log"
        >
          <div
            class="list-group-item"
            v-for="(element, index) in list3"
            :key="element.name"
          >
            {{ element.name }} {{ index }}
          </div>
        </draggable>
      </el-col>
    </el-row>
  </div>
</template>
<script>
import draggable from "vuedraggable";

export default {
  name: "BoardTasks",
  display: "Two Lists",
  order: 1,
  components: {
    draggable,
  },
  data() {
    return {
      list1: [
        { name: "John", id: 1 },
        { name: "Joao", id: 2 },
        { name: "Jean", id: 3 },
        { name: "Gerard", id: 4 },
      ],
      list2: [
        { name: "Juan", id: 5 },
        { name: "Edgard", id: 6 },
        { name: "Johnson", id: 7 },
      ],
      list3: [
        { name: "Jua", id: 8 },
        { name: "Edgard", id: 9 },
        { name: "Johnson", id: 10 },
      ],
    };
  },
  methods: {
    add: function () {
      this.list.push({ name: "Juan" });
    },
    replace: function () {
      this.list = [{ name: "Edgard" }];
    },
    clone: function (el) {
      return {
        name: el.name + " cloned",
      };
    },
    log: function (evt) {
      console.log(evt);
    },
  },
};
</script>

<style>
h3 {
  text-align: center;
}
.table-row .el-row {
  justify-content: center;
  display: flex;
}
.table-row .el-col {
  justify-content: center;
  display: inline-grid;
}
.list-group-item {
  padding: 10px;
  border: 1px solid red;
}
</style>
