<template>
  <a-table
    :columns="columns"
    :data-source="data"
    :row-selection="rowSelection"
    :expanded-row-keys.sync="expandedRowKeys"
  />
</template>
<script>
const columns = [
  {
    title: '币种',
    dataIndex: 'currency',
    key: 'currency',
    width: '20%',
  },
  {
    title: '类别',
    dataIndex: 'updom',
    key: 'name',
    width: '20%',
  },
  {
    title: '数量',
    dataIndex: 'nummoney',
    width: '20%',
    key: 'nummoney',
  },
  {
    title: '转账类型',
    dataIndex: 'transfertype',
    width: '20%',
    key: 'transfertype',
  },
  {
    title: '使用者UID',
    dataIndex: 'uid',
    width: '20%',
    key: 'uid',
  },
];

const data = [
  {
    key: 1,
    currency: 'HALO',
    updom: '转出',
    nummoney:'10000',
    transfertype: '内转',
    uid: '000001',
  },

];

const rowSelection = {
  onChange: (selectedRowKeys, selectedRows) => {
    console.log(`selectedRowKeys: ${selectedRowKeys}`, 'selectedRows: ', selectedRows);
  },
  onSelect: (record, selected, selectedRows) => {
    console.log(record, selected, selectedRows);
  },
  onSelectAll: (selected, selectedRows, changeRows) => {
    console.log(selected, selectedRows, changeRows);
  },
};

export default {
  data() {
    return {
      data,
      columns,
      rowSelection,
      expandedRowKeys: [],
    };
  },
};
</script>
