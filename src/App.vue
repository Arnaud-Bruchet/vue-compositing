<template>
  <div id="app">
    <!-- app est notre parent dans cette composition  -->
    <div class="row">
      <div class="col left">
        <CciImage imgLegend="Billy" />
        <CciImage
          imgSrc="https://idata.over-blog.com/0/19/24/98/Cheval-viande-drole/lasagne-cheval-cannibale-bd-humour-restaurant.jpg"
          imgLegend="Lasagne" />
        <ul>
          <li v-for="(cardId,index) in selectedCourse" :key="index">
            {{ coursesInfos[cardId].chapter }}
          </li>
        </ul>
      </div>
      <div class="col right">
        <div>
          <CciCard :chapterTitle="coursesInfo.chapter" :chapterNumber="coursesInfo.chapterNumber"
            :coursesColor="coursesInfo.color" v-for="(coursesInfo,index) in coursesInfos" :key="index" :cardId="index"
            @onCourseSelected="handleCourseSelected" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>

// First component import
import CciCard from './components/CciCard'
import CciImage from './components/CciImage.vue';


export default {
  name: "App",
  components: {
    CciCard,
    CciImage
  },
  props: {
    
  },  
  data: () => ({
    selectedCourse: [],
    coursesInfos: [
      {
        chapter: "Vue.JS",
        chapterNumber: 2,
        color: "lime",
      },
      {
        chapter: "JS",
        chapterNumber: 3,
        color: "#EBE60E",
      },
      {
        chapter: "Javascript",
        chapterNumber: 4,
        color: "#ED6FF5",
      },
      {
        chapter: "Javascript encore",
        chapterNumber: 8,
        color: "#FF0000",
      },
      {
        chapter: "Javascript et oui encore",
        chapterNumber: 4,
      },
    ],
  }),
  methods: {
    handleCourseSelected(datas) {
      console.log("🧑 événement entendu par le parent", datas)

      if (!this.selectedCourse.includes(datas.cardId)){
        this.selectedCourse.push(datas.cardId)
      }
    }
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Muli&display=swap");
#app {
  display: flex;
  margin-left: 5%;
  margin-top: 2%;
  margin-right: 5%;
}
.row {
  margin-top: 10px;
  width: 100%;
  display: flex;
}
.col {
  padding: 50px;
  color: cyan;
  font-family: "Muli", sans-serif;
}
.left {
  width: 20%;
  font-size: 24px;
  background-color: #065a75;
}
.right {
  width: 70%;
}

.btn {
  background-color: #2a265f;
  border: 0;
  border-radius: 10px;
  box-shadow: 0 10px 10px rgba(0, 0, 0, 0.2);
  color: #fff;
  font-size: 16px;
  padding: 12px 25px;
  position: absolute;
  bottom: 30px;
  right: 30px;
  letter-spacing: 1px;
}
</style>
