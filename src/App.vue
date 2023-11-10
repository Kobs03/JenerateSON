<template>
  <!-- <div>
    key: <input type="text" placeholder="Object Key" /> 
    value: <input type="text" placeholder="Object Value" /> &nbsp;
    <button> X </button> &nbsp;
    <button> + </button>
  </div> -->

  <div class="d-flex justify-content-center" v-if="objectData.length === 0">
    add key value pairs &nbsp;
    <button @click="add">+</button>
  </div>

  <div v-for="obj in objectData" :key="obj.id">
    <br />
    key: <input type="text" /> value: <input type="text" /> &nbsp;
    <button @click="add">+</button> &nbsp;
    <button @click="del">X</button>
    <br />
  </div>
  <br />
  <div v-if="!objectData.length == 0" class="d-flex justify-content-center">
    <button>Submit!</button>
  </div>
</template>

<script>

// Proj name on release "JSONizer"

//**********STRUCTURE**************/

// pre template
// [
//  main object loop
//   {
//     *** where the form loops for the key and value pairs
//      format -> "{{ key }}" : " {{ value }} "
//   },
//  upon submitting the key value pairs, create new obj
// ]

// 

export default {
  data() {
    return {
      index: -1,
      param1: "",
      param2: "",
      objectData: [],
    };
  },

  methods: {
    add() {
      this.index += 1;
      this.objectData.push({
        id: this.index,
        key: this.param1,
        value: this.param2,
      });
    },

    del() {
      this.objectData.splice(this.index, 1);
      this.index -= 1;
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/sass/styles.scss";
</style>