<template>
  <div>
    <TransferList
      :enhanced="true"
      :initValues="initValues"
      :transfferdItems="transfferdItems"
      :editable="true"
      :lessthanImage="lessthanImage"
      :largeThanImage="largeThanImage"
      :allMoveRightImage="allMoveRightImage"
      :allMoveLeftImage="allMoveLeftImage"
      :viewAllTransferBtn="true"
      @onChangedValues="updatedTransferList"
    />
  </div>
</template>

<script>
import TransferList from "./components/TransferList.vue";
export default {
  name: "App",
  components: {
    TransferList,
  },
  data() {
    return {
      initValues: [],
      transfferdItems: [],
      transfferdItemslist: [],
      lessthanImage: "<",
      largeThanImage: ">",
      allMoveRightImage: ">>",
      allMoveLeftImage: "<<",
    };
  },
  created() {
    this.initValues = [
      {
        id: 1,
        name: "List Item1",
        value: "item1",
      },
      {
        id: 2,
        name: "List Item2",
        value: "item2",
      },
      {
        id: 3,
        name: "List Item3",
        value: "item3",
      },
      {
        id: 4,
        name: "List Item4",
        value: "item4",
      },
      {
        id: 5,
        name: "List Item5",
        value: "item5",
      },
      {
        id: 6,
        name: "List Item6",
        value: "item6",
      },
      {
        id: 7,
        name: "List Item7",

        value: "item7",
      },
      {
        id: 8,
        name: "List Item8",
        value: "item8",
      },
    ];

    this.transfferdItems = ["item4", "item5"];
  },
  method: {
    updatedTransferList() {
      console.lo("updatedTransferList");
      alert("updatedTransferList")

      // this.transfferdItems = [];
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.redTheame {
  color: red;
}
.greenThame {
  color: green;
}
</style>
