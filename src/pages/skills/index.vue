<template>
  <div class="page skills">
    <h1 class="title" style="font-family: cursive;">{{ $store.state.data.route[id] }}</h1>
    <div class="pagebody">
      <div class="radar"></div>
      <div class="skillsContent">
        <ul>
          <li>掌握HTML/CSS,实现静态页面</li>
          <li>熟练使用ES6语法,包括let / Promise / await /解析赋值等</li>
          <li>
            掌握
            <span>前后端分离技术</span>,包括Ajax/axios网络请求的封装使用,跨域,前端路由,Cookie,Session,jQuery,jwt
          </li>
          <li>
            掌握
            <span>组件化开发</span>,包括ElementUI组件的熟练使用,组件的封装使用
          </li>
          <li>
            掌握
            <span>Vue全家桶的使用</span>,包括Vuex,VueRouter,Vue-Cli等
          </li>
          <li>
            了解
            <span>Webpack的配置和优化</span>
          </li>
          <li>
            了解
            <span>后端相关技术</span>,包括Node/MySql/MongoDB/Nginx配置和项目的部署
          </li>
          <li>
            <span>编程基础</span>,包括有数据结构与算法,计算机网络基础,可以在linux系统操作和部署项目,git命令的使用
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "skills",
  props: ["id", "show"],
  data: () => {
    return {
      mShow: false
    };
  },

  watch: {
    show: function(val, oldVal) {
      let vm = this;
      if (val) {
        setTimeout(function() {
          vm.mShow = true;
        }, 500);
      } else {
        vm.mShow = false;
      }
    }
  },
  mounted() {
    this.renderRadar();
  },
  methods: {
    renderRadar() {
      var myChart = echarts.init(document.querySelector(".radar"));

      // 指定图表的配置项和数据
      var option = {
        radar: {
          name: {
            textStyle: {
              color: "#fff",
              backgroundColor: "#000",
              borderRadius: 3,
              padding: [3, 5]
            }
          },
          indicator: [
            { name: "静态页面(HTML/CSS)", max: 80 },
            { name: "Vue/Webpack", max: 100 },
            { name: "前后端分离技术", max: 100 },
            { name: "后端技术(Node/MySql/MongoDB/Java/Nginx)", max: 100 },
            { name: "编程基础", max: 100 },
            { name: "沟通能力", max: 100 }
          ]
        },
        series: [
          {
            name: "技能雷达图",
            type: "radar",
            data: [
              {
                value: [80, 70, 80, 60, 85, 80],
                name: "技能雷达图"
              }
            ]
          }
        ]
      };

      // 使用刚指定的配置项和数据显示图表。
      myChart.setOption(option);
    }
  }
};
</script>

<style lang="less" scoped>
@import "index.less";
</style>
