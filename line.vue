<template>
  <div>
    <div class="ss" id="main"></div>
  </div>
</template>

<script>
export default {
  mounted() {
    var wy = this.echarts.init(document.getElementById("main"));
    var option = {
      // 标题
      title: {
        text: "王勇的line-Echarts"
      },
      // 提示框
      tooltip: {
        trigger: "axis"
      },
      // 图例
      legend: {
        data: ["最高", "最低"]
      },
      // 工具
     toolbox: {
        show: true, //显示还是隐藏
        feature: {
          //各工具配置项
          dataView: {
            //数据视图是否可见
            show: true,
            readOnly: true //是否为只读
          },
          magicType: {
            //动态类型切换
            show: true,
            type: ["line", "bar"] //切换成折线图或者柱形图
          },
          restore: {
            //刷新
            show: true
          },
          saveAsImage: {
            //是否下载
            show: true
          }
        }
      },
      xAxis: {
        type: "category",
        data: (function() {
          //写一个匿名函数循环出1-12拼接月字   2020-03-xx  也是同理
          var list = [];
          for (var i = 1; i <= 12; i++) {
            list.push(i + "月");
          }
          return list;
        })() //调用匿名函数
      },
      yAxis: {
        type: "value"
      },
      dataZoom: [
        {
          show: true,
          start: 0,
          end: 100
        }
      ],
      series: [
        {
          data: (function() {
            var list = [];
            for (var i = 1; i <= 12; i++) {
              list.push(Math.round(Math.random() * 30));    //在30中随机取整数值
            }
            return list;
          })(),
          type: "line",
          name: "最高"
        },
        {
          data: (function() {
            var list = [];
            for (var i = 1; i <= 12; i++) {
              list.push(Math.round(Math.random() * 10));  //在10中随机取整数值
            }
            return list;
          })(),
          type: "line",
          name: "最低"
        }
      ]
    };
    wy.setOption(option);
  },
};
</script>

<style>
</style>