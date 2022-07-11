<template>
  <div>
    <img
      width="240px"
      :src="imgSrc"
      alt=""><br>
      <span class="legende">{{imgLegend}}</span>
  </div>
</template>

<script>

export default {
  name: "CciImage",
  created() {},
  data: () => ({

  }),
  props: {
    imgSrc: {
      type: String,
      default: "https://i0.wp.com/lesoreillescurieuses.com/wp-content/uploads/2022/01/19F8C7DC-CEEF-45CB-9C17-A1C698337856.jpeg?fit=640%2C640&ssl=1"
    },
    imgLegend: {
      type: String,
      default: "Aucune légende"
    }
  },
  methods: {},
};
</script>

<style scoped>
  div {
    text-align: center;
  }

  img{
    border-radius: 10px;
    margin-top: 20px;
  }

  .legende{
    color:white;
    font-size: medium;
  }

</style>