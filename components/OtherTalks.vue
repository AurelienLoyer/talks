<template>
    <div class="others">
        <h3>Other talks</h3>
        <div class="list">
            <v-talk v-for="(talk,index) in talks" v-if="talk.uname !== exclude" :key="`talk-${index}`" :talk="talk"></v-talk>
        </div>
    </div>
</template>


<script>
import talks from "../talks.json";
import Talk from "./Talk";

export default {
  props: ["exclude"],
  data() {
    return {
      talks
    };
  },
  components: {
    "v-talk": Talk
  }
};
</script>

<style scoped lang="scss">
.others {
  width: 100%;
  padding: 5%;
  .list {
    width: 1200px;
    margin: auto;
  }
}
</style>
