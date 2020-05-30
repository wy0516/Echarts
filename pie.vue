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
      title: {
        text: "某站点用户访问来源",
        subtext: "纯属虚构",
        left: "center"
      },

      tooltip: {
        trigger: "item",
        formatter: "{a} <br/>{b} : {c} ({d}%)" // * {a}（系列名称），{b}（数据项名称），{c}（数值）, {d}（百分比）
      },
      legend: {
        orient: "vertical",
        left: "left",
        data: ["学生", "讲师", "班主任"]
      },
      calculable: true,
      series: [
        {
          name: "访问来源",
          type: "pie",
          radius: "55%", //图片占div的 百分比
          center: ["50%", "50%"], //圆心的坐标
          data: [
            { value: 34, name: "学生" },
            { value: 1, name: "讲师" },
            { value: 1, name: "班主任" }
          ],
          emphasis: {
            itemStyle: {
              shadowBlur: 10,
              shadowOffsetX: 0,
              shadowColor: "rgba(0, 0, 0, 0.5)"
            }
          }
        }
      ]
    };
    wy.setOption(option);
  }
};
</script>

<style>
.ss {
  width: 500px;
  height: 500px;
  margin: 50px auto;
}
</style>