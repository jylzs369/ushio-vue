<template>
  <div id="app">
    <img class="logo" src="./assets/logo.png">
    <hello></hello>
    <button @click="checkUnusual">异常率</button>
    <button @click="checkSign">签到率</button>
    <div class="chart">
      <div class="main"></div>
    </div>
  </div>
</template>

<script>
import Hello from './components/Hello'
import echarts from 'echarts'

export default {
  components: {
    Hello,
    echarts
  },
  data () {
    return {}
  },
  created () {
    this.unusual = [
      {
        department: '金域华府',
        rates: [18.2, 19.1, 17.5, 16.4]
      },
      {
        department: '司机化成',
        rates: [18.2, 19.1, 17.5, 16.4]
      },
      {
        department: '四季花城',
        rates: [18.2, 19.1, 17.5, 16.4]
      },
      {
        department: '啦啦啦啦',
        rates: [18.2, 19.1, 17.5, 16.4]
      },
      {
        department: '森林公园',
        rates: [18.2, 19.1, 17.5, 16.4]
      },
      {
        department: '露出',
        rates: [18.2, 19.1, 17.5, 16.4]
      },
      {
        department: '乌鲁木齐石化的',
        rates: [18.2, 19.1, 17.5, 16.4]
      },
      {
        department: '金域华府2',
        rates: [18.2, 19.1, 17.5, 16.4]
      },
      {
        department: '金域华府3',
        rates: [18.2, 19.1, 17.5, 16.4]
      },
      {
        department: '金域华2府',
        rates: [18.2, 19.1, 17.5, 16.4]
      },
      {
        department: '金域4华府',
        rates: [16.2, 15.1, 17.5, 16.4]
      }
    ]
    this.initChart(this.unusual, 'unusual')
  },
  methods: {
    checkUnusual () {
    },
    checkSign () {
      let sign = [
        {
          department: '金域华府',
          rates: [18.2, 19.1, 17.5, 16.4]
        },
        {
          department: '司机化成',
          rates: [18.2, 19.1, 17.5, 16.4]
        },
        {
          department: '四季花城',
          rates: [18.2, 19.1, 17.5, 16.4]
        },
        {
          department: '啦啦啦啦',
          rates: [18.2, 19.1, 17.5, 16.4]
        },
        {
          department: '森林公园',
          rates: [18.2, 19.1, 17.5, 16.4]
        },
        {
          department: '露出',
          rates: [18.2, 19.1, 17.5, 16.4]
        },
        {
          department: '乌鲁木齐石化的',
          rates: [18.2, 19.1, 17.5, 16.4]
        },
        {
          department: '金域华府2',
          rates: [18.2, 19.1, 17.5, 16.4]
        },
        {
          department: '金域华府3',
          rates: [18.2, 19.1, 17.5, 16.4]
        },
        {
          department: '金域华2府',
          rates: [18.2, 19.1, 17.5, 16.4]
        },
        {
          department: '金域4华府',
          rates: [16.2, 15.1, 17.5, 16.4]
        }
      ]
    },
    initChart (data, type) {
    }
  },
  mounted () {
    let options = {
    title: {
        text: '世界人口总量',
        subtext: '数据来自网络'
    },
    tooltip: {
        trigger: 'axis',
        axisPointer: {
            type: 'shadow'
        }
    },
    legend: {
        data: ['2011年', '2012年']
    },
    grid: {
        left: '3%',
        right: '4%',
        bottom: '3%',
        containLabel: true
    },
    xAxis: {
        type: 'value',
        boundaryGap: [0, 0.01]
    },
    yAxis: {
        type: 'category',
        data: ['巴西','印尼','美国','印度','中国','世界人口(万)']
    },
    series: [
        {
            name: '2011年',
            type: 'bar',
            data: [18203, 23489, 29034, 104970, 131744, 630230]
        },
        {
            name: '2012年',
            type: 'bar',
            data: [19325, 23438, 31000, 121594, 134141, 681807]
        }
    ]
    } 
    this.myChart = echarts.init(document.querySelector('.chart .main'));
    this.myChart.setOption(options);
  }
}
</script>

<style>
html {
  height: 100%;
}
* {
  padding: 0;
  margin: 0;
}
body {
  /*display: flex;*/
  align-items: center;
  justify-content: center;
  height: 100%;
}

#app {
  color: #2c3e50;
  margin-top: -100px;
  /*max-width: 600px;*/
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
}

#app a {
  color: #42b983;
  text-decoration: none;
}

.logo {
  width: 100px;
  height: 100px
}

.chart {
  width: 100%;
}
.main {
  height: 20em;
}
</style>
