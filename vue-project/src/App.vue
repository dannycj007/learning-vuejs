<script >
import axios from "axios";
export default {
  data() {
    return {
      items: [],
      paginate: ["items"],
    };
  },
  created() {
    this.loadPressRelease();
  },
  methods: {
    loadPressRelease() {
      axios.get(`https://zbeta2.mykuwaitnet.net/backend/en/api/v2/media-center/press-release/?page_size=61&type=5`)
        .then((response) => {
          this.items = response.data.results;
        });
    }
  }
};
</script>

<template>
  <div id="app">
    <paginate ref="paginator" class="flex-container" name="items" :list="items">
      <li v-for="(item, index) in paginated('items')" :key="index" class="flex-item">
        <h4>{{ item.pub_date }}, {{ item.title }}</h4>
        <img :src="item.image && item.image.file" />
        <div class="downloads">
          <span v-for="downloadable in item.downloadable.filter(
            (d) => !!d.document_en
          )" :key="downloadable.id">
            <a :href="downloadable.document_en.file">Download</a>
          </span>
        </div>
      </li>
    </paginate>
    <paginate-links for="items" :limit="2" :show-step-links="true"></paginate-links>
  </div>
</template>

<style scoped>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

ul.flex-container {
  padding: 0;
  margin: 0;
  list-style-type: none;
  display: -webkit-box;
  display: -moz-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  flex-flow: row wrap;
  flex-direction: row wrap;
  flex-wrap: wrap;
  justify-content: space-around;
}

li img {
  display: initial;
  height: 100px;
}

.flex-item {
  background: tomato;
  width: calc(100% / 3.5);
  padding: 5px;
  height: auto;
  margin-top: 10px;
  color: white;
  font-weight: bold;
  text-align: center;
}

.downloads {
  margin-top: 10px;
}

ul.paginate-links.items li {
  display: inline-block;
  margin: 5px;
}

ul.paginate-links.items a {
  cursor: pointer;
}

ul.paginate-links.items li.active a {
  font-weight: bold;
}

ul.paginate-links.items li.next:before {
  content: " | ";
  margin-right: 13px;
  color: #ddd;
}

ul.paginate-links.items li.disabled a {
  color: #ccc;
  cursor: no-drop;
}
</style>
