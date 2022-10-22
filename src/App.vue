<template>
  <div class="container">
    <div class="main">
      <div class="main-title">
        <div demo-bg>
          <dv-border-box9>
            <div class="dv-bg" dv-bg>
              <div class="title-text">哈哈哈哈哈</div>
              <div class="title-text center">政务云资源总览</div>
              <div class="title-text">巴卡马卡把卡</div>
            </div>
          </dv-border-box9>
        </div>
      </div>
      <div class="main-table">
        <div v-for="item in tablesText" small-bg>
          <dv-decoration-11 style="width:200px;height:60px;color: white">
            <div bg="~ dark/0" color-green font-600>
              <div>{{ item }}</div>
            </div>
          </dv-decoration-11>
        </div>
      </div>

      <div class="main-content">
        <!--左边-->
        <div class="main-label">
          <div class="label-title">标题吃喜羊羊哈哈</div>
          <div class="main-label-table">
            <div v-for="item in mainlable" class="table-item">{{ item }}</div>
          </div>
          <el-pagination
              :total="50"
              background
              class="mt-4 bg"
              layout="prev, pager, next"
              small
          />
        </div>
        <div class="main-statistics"></div>
        <!--右边-->
        <div class="main-label">
          <div class="label-title">标题吃喜羊羊哈哈</div>
          <div class="main-label-table">
            <div v-for="item in mainlable" class="table-item">{{ item }}</div>
          </div>
          <el-pagination
              :total="50"
              background
              class="mt-4 bg"
              layout="prev, pager, next"
              small
          />
        </div>
      </div>
    </div>
    <div class="foot">
      <div class="zhu-zhuang-tu">
        <div class="label-title">表格</div>
        <div class="first-table">
          <el-table id="my-table" :data="tableData" style='width:100%' >
            <el-table-column prop="date" align="center" label="date" width="80"/>
            <el-table-column label="cpu" align="center">
              <el-table-column prop="cpu1" align="center" label="" width="43"/>
              <el-table-column prop="cpu2" align="center" label="" width="43"/>
            </el-table-column>
            <el-table-column label="gpu" align="center">
              <el-table-column prop="gpu" align="center" label="" width="43"/>
              <el-table-column prop="gpu" align="center" label="" width="43"/>
            </el-table-column>
            <el-table-column label="qbb" align="center">
              <el-table-column prop="gpu" align="center" label="" width="43"/>
              <el-table-column prop="gpu" align="center" label="" width="43"/>
            </el-table-column>
          </el-table>
        </div>
      </div>
      <div class="zhu-zhuang-tu" v-for="item in footTitle">
        <div class="label-title">{{ item.title }}</div>
        <myTable :colors="item.colors" :data="item.data"/>
      </div>
    </div>
  </div>
</template>
<script setup>
import {reactive} from "vue";
import myTable from "./components/tabel.vue";

const tablesText = reactive(['CJIA', 'ISQS', 'JSIQ', 'DXG', 'UIHXDU'])
const footTitle = $ref([
  {
    title: 'CPU',
    colors: [
      '#b186a1',
      '#664f97',
      '#584572'
    ],
    data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
  }, {
    title: 'CPU2',
    colors: [
      '#ceacb3',
      '#9a7b81',
      '#936886'
    ],
    data: ["吃饭", "是阿三", "和地区的", "裤i欧家栋i哦子", "嗲u好地方", "袜子"]
  }, {
    title: 'CPU3',
    colors: [
      'rgba(213,171,168,0.76)',
      '#f3796b',
      '#da4d61'
    ],
    data: ["123", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "www"]
  },
])
const tableData = [
  {
    date: '2022/10/23',
    cpu1: 222,
    cpu2: 333,
    gpu: 200,
    qb: 300,
  }, {
    date: '2022/10/24',
    cpu1: 44,
    cpu2: 55,
    gpu: 200,
    qb: 300,
  }, {
    date: '2022/10/25',
    cpu1: 100,
    cpu2: 100,
    gpu: 200,
    qb: 300,
  }, {
    date: '2022/10/26',
    cpu1: 100,
    cpu2: 100,
    gpu: 200,
    qb: 300,
  },
]

const mainlable = $ref(['数据1', '数据1', '数据1', '数据1', '数据1', '数据1', '数据1', '数据1', '数据1', '数据1', '数据1', '数据1'])
</script>

<style lang="scss" scoped>
//::v-deep(#my-table tr:nth-child(2) > th:nth-child(2n)) {
//  border-left: none;
//}
::v-deep(#my-table .is-group tr:nth-child(2) ) {
  display: none;
}

//::v-deep(#my-table tr:nth-child(2) > th:nth-child(2n -1)) {
//  border-right: none !important;
//}

.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  background: rgb(10, 10, 30);

  .main {
    flex: 1;
    border: 2px solid rgb(6, 158, 224);

    .dv-bg {
      width: 100%;
      height: 100px;
      display: flex;
      justify-content: center;
      align-items: center;

      .title-text {
        padding: 0 22px;
        font-size: 23px;
        color: rgb(140, 144, 151);
      }

      .center {
        color: white;
        font-size: 33px;
      }
    }

    .main-table {
      display: flex;
      justify-content: space-around;
      margin-top: 10px;
    }

    .main-content {
      display: flex;
      justify-content: space-between;

      .main-label {
        margin-top: 20px;

        ::v-deep(.el-pagination) {
          margin-left: 19px;
          margin-bottom: 9px;

          button, li {
            color: #fff;
            background: rgb(35, 56, 69);

            &.is-active {
              background: rgb(28, 131, 145);
            }
          }
        }

        .main-label-table {
          width: 200px;
          height: 280px;
          margin: 10px 30px 0;
          display: flex;
          align-content: flex-start;
          flex-flow: wrap;
          justify-content: space-between;

          .table-item {
            border: 2px solid rgb(6, 158, 224);
            border-radius: 5px;
            width: 94px;
            height: 33px;
            margin-bottom: 10px;
            color: white;
            line-height: 33px;
            text-align: center;
            font-size: 12px;
          }
        }
      }

      .main-statistics {
        width: 300px;
        height: 300px;
        border: 2px solid rgb(6, 158, 224);
        border-radius: 50%;
        margin-top: 33px;
      }
    }
  }

  .foot {
    flex: 1;
    display: flex;
    flex-direction: row;
    justify-content: center;
    margin-top: 5px;
    overflow: hidden;

    .first-table {
      color: #fff;
      width: 90%;
      padding-left: 20px;
      margin-top: 8px;

      ::v-deep(.el-table .cell) {
        padding: 0 2px;
        line-height: 14px
      }

      ::v-deep(.el-table__body td.el-table__cell) {
        background: rgb(10, 10, 30);
        color: #fff;
        border: 1px solid #333
      }

      ::v-deep(.el-table thead.is-group th.el-table__cell) {
        background: rgb(10, 10, 30);
        color: #ddd;
        border: none;

      }

      ::v-deep(.el-table thead.is-group th.el-table__cell) {
        border-right: 1px solid #333 !important;
      }

    }

    .zhu-zhuang-tu {
      flex: 1;
      border: 2px solid rgb(6, 158, 224);
      margin-left: 5px;

      .label-title {
        font-size: 14px;
        margin-top: 5px;
      }

      .tubiao {
        width: 300px;
        height: 250px;
        margin-top: -38px;
        margin-left: 6px;
      }
    }
  }
}

.label-title {
  color: #fff;
  font-weight: 400;
  font-size: 16px;
  position: relative;
  margin-left: 20px;
  flex: 1;

  &:after {
    content: '';
    display: block;
    width: 6px;
    height: 16px;
    background: rgb(6, 255, 255);
    border-radius: 8px;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    left: -12px;
  }
}
</style>
