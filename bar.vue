<template>
  <div class="hello">
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
        text: "王勇的Bar-Echarts",
        left:"left",  //水平对齐的方式  center/left/right/数值
        top:"0",  //垂直对齐的方式  center/left/right/数值
        backgroundColor:"#000000",  //设置背景颜色
        textStyle:{   //设置字体样式
          color:"#fff",  //设置字体颜色
          // fontSize:"12px",  //设置字体的大小
          fontWeight:"bold",  //设置字体的粗细  bold(粗体)/lighter(细体)/数值
          fontStyle:"normal",  //设置字体的风格  italic(斜体)/normal(正常)
        },
        subtext:"全都是泡沫",  //副标题
        borderWidth:3,  //边框宽度
        borderColor:"red",  //边框颜色
      },
      // 提示框
      tooltip: {
        // 可以设置颜色、边框、文本样式
        trigger: "axis", //两个取值  item/axis
      },
      // 图例
      legend: {
        // 可以设置水平位置和垂直位置,边框,边框颜色
        data: ["蒸发", "降水"], //开关下面对应的
        inactiveColor:"#ccc",  //图片关闭时的颜色
      },
      // 工具栏
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
      // X轴
      xAxis: [
        {
          type: "category", //坐标轴类型 'value' 数值轴、'category' 类目轴、'time' 时间轴、'log' 对数轴
          data: ["1", "2", "3", "4", "5"]  //X轴内容
        }
      ],
      // Y轴
      yAxis: [
        { type: "value" } //坐标轴类型 'value' 数值轴、'category' 类目轴、'time' 时间轴、'log' 对数轴
      ],
      // 序列
      series: [
        // 可以写多个数据
        {
          name: "蒸发",   //数据的名称，对应图例中的data
          type: "bar",   //切换成折线图或者柱形图
          data: [2, 11, 55, 88, 188]  //对应X轴中的数据
        },
        {
          name: "降水",
          type: "bar", 
          data: [2, 17, 66, 78, 288]  
        },
        
      ]
    };
    wy.setOption(option);
  },
};
</script>

<style>
.ss {
  width: 500px;
  height: 500px;
  margin: 50px auto;
}
</style>