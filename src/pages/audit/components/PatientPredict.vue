<template>
  <!-- 患者领药计划模块 start-->
  <div class="plan_module">
    <!-- 标题 -->
    <div class="title_box">
      <h3>患者领药计划</h3>
    </div>
    <!-- 选择器 -->
    <div class="select_outer">
      <ul>
        <li class="select_li">
          <p>所在省份</p>
          <el-select v-model="value" placeholder="选择所在省份">
            <el-option
              v-for="item in province"
              :key="item.province_value"
              :label="item.province_label"
              :value="item.province_value"
            >
            </el-option>
          </el-select>
        </li>
        <li class="select_li">
          <p>所在城市</p>
          <el-select v-model="city_value" placeholder="选择所在城市">
            <el-option
              v-for="item in cities"
              :key="item.city_value"
              :label="item.city_label"
              :value="item.city_value"
            >
            </el-option>
          </el-select>
        </li>
        <li class="select_li">
          <p>药房查询</p>
          <el-select v-model="city_value" placeholder="选择药房">
            <el-option
              v-for="item in drugstore"
              :key="item.drugstore_value"
              :label="item.drugstore_label"
              :value="item.drugstore_value"
            >
            </el-option>
          </el-select>
        </li>
        <li class="select_li">
          <p>药品查询</p>
          <el-select v-model="city_value" placeholder="选择药品">
            <el-option
              v-for="item in drugstore"
              :key="item.drugstore_value"
              :label="item.drugstore_label"
              :value="item.drugstore_value"
            >
            </el-option>
          </el-select>
        </li>
      </ul>
      <div>
        <p>患者姓名</p>
        <el-input v-model="input1" placeholder="请输入患者姓名"></el-input>
      </div>
    </div>
    <!-- 日期选择 -->
    <div class="date_box">
      <!-- <span class="demonstration">带快捷选项</span> -->
      <el-date-picker
        v-model="value2"
        type="daterange"
        unlink-panels
        range-separator="至"
        start-placeholder="开始日期"
        end-placeholder="结束日期"
        :shortcuts="shortcuts"
      >
      </el-date-picker>
      <el-button class="search_btn" size="small" type="primary" round
        >查询</el-button
      >
    </div>
    <!-- Table 表格 -->
    <el-table :data="tableData" border style="width: 100%" align="center">
      <el-table-column prop="name" label="患者姓名" width="180" align="center">
      </el-table-column>
      <el-table-column prop="phone" label="患者电话" width="180" align="center">
      </el-table-column>
      <el-table-column prop="drug" label="药品名称规格" align="center">
      </el-table-column>
      <el-table-column prop="num" label="数量" align="center">
      </el-table-column>
      <el-table-column prop="get_state" label="领药状态" align="center">
      </el-table-column>
      <el-table-column prop="lock_state" label="锁定状态" align="center">
      </el-table-column>
      <el-table-column prop="pause_state" label="暂停状态" align="center">
      </el-table-column>
    </el-table>
    <!-- 分页 -->
    <div class="page_box">
      <el-pagination background layout="prev, pager, next" :total="1000">
      </el-pagination>
    </div>
  </div>
  <!-- 患者领药计划模块 end-->
</template>

<script>
export default {};
</script>

<style></style>
