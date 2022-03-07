<template>
  <div>
    <BoardTasks />
    <RightMenu />
  </div>
</template>
<script>
import BoardTasks from "./components/board/BoardTasks";
import RightMenu from "./components/rightMenu/RightMenu";

export default {
  name: "App",
  components: {
    BoardTasks,
    RightMenu,
  },
};
</script>
