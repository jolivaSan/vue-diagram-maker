<template>
    <div data-event-target="true" data-dropzone="true">
        <h4>Nodes</h4>
        <el-divider></el-divider>
        <div class="panel-inset">
          <el-input placeholder="Filter..." prefix-icon="el-icon-search" v-model="filter"></el-input>
          <div class="panel-section">Adapters</div>
          <NodeToCreate v-for="adapter in adapter_list" :key="adapter.adapter_id"
          :adapter_id="adapter.adapter_id" :adapter_name="adapter.adapter_name">
          </NodeToCreate>
          <div class="panel-section">Selectors</div>
        </div>
    </div>
</template>

<script>
import NodeToCreate from './NodeToCreate.vue'
export default {
  components: { NodeToCreate },
  data () {
    return {
      filter: null,
      adapter_list: [{
        adapter_id: 'Password',
        adapter_name: 'Password Adapter'
      },
      {
        adapter_id: 'OTP',
        adapter_name: 'OTP Adapter'
      }]
    }
  },
  methods: {}
}
</script>

<style>
.dm-panel {
  border-top: 0px;
  box-shadow: none;
  border-left: 1px solid #e6e6e6;
}
.panel-section {
  color: #909399;
  font-size: 13px;
  font-weight: bold;
  padding: 20px 0px 0px;
}
.dm-panel .dm-content {
  padding: 0px;
}
.dm-panel .dm-content h4 {
  margin: 0px;
  padding: 10px 20px 0px;
  color: #324a5e;
}
.dm-panel .dm-content .el-divider.el-divider--horizontal {
  margin: 10px 0px;
}
.panel-inset {
 padding: 10px 20px;
}
.panel-inset .node-adapter {
  margin-top: 10px;
}
</style>
