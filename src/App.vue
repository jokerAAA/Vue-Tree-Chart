<template>
  <div id="app">
    <TreeChart :json="data" @click-node="clickNode" />
    <footer class="foot">
        <p>© 2018 - 3018  Author
            <a href="https://refined-x.com/" target="_blank">雅X共赏</a> 
        </p>
    </footer>
  </div>
</template>

<script>
//import TreeChart from "vue-tree-chart";
import TreeChart from "../lib/components/TreeChart.vue";

export default {
  name: 'app',
  components: {
    TreeChart
  },
  data() {
    return {
      data: {
        name: 'root',
        image_url: "https://static.refined-x.com/avat.jpg",
        children: [
          {
            name: 'children1',
            image_url: "https://static.refined-x.com/avat1.jpg"
          },
          {
            name: 'children2',
            image_url: "https://static.refined-x.com/avat2.jpg",
            mate: {
              name: 'mate',
              image_url: "https://static.refined-x.com/avat3.jpg"
            },
            children: [
              {
                name: 'grandchild',
                image_url: "https://static.refined-x.com/avat.jpg"
              },
              {
                name: 'grandchild2',
                image_url: "https://static.refined-x.com/avat1.jpg"
              },
              {
                name: 'grandchild3',
                image_url: "https://static.refined-x.com/avat2.jpg"
              }
            ]
          }
        ]
      }
    }
  },
  methods: {
    clickNode: function(node){
      // eslint-disable-next-line
      console.log(node)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#app .avat{border-radius: 2em;border-width:2px;}
#app .name{font-weight:700;}
.foot {
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
    background: #333;
    padding: 24px;
    overflow: hidden;
    color: #999;
    font-size: 14px;
    text-align: center;
}
.foot a{color:#fff;margin:0 .5em}
</style>
