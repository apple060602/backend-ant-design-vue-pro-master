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
    title: '用戶uid',
    dataIndex: 'uid',
    key: 'uid',
    width: '20%',
  },
  {
    title: '姓名',
    dataIndex: 'name',
    key: 'name',
    width: '20%',
  },
  {
    title: '手機',
    dataIndex: 'phone',
    width: '20%',
    key: 'phone',
  },
  {
    title: '信箱',
    dataIndex: 'address',
    width: '20%',
    key: 'address',
  },
  {
    title: '谷哥',
    dataIndex: 'googleaccount',
    width: '20%',
    key: 'googleaccount',
  },
];

const data = [
  {
    key: 1,
    uid: '000001',
    name: 'John',
    phone:'091234567',
    age: 60,
    address: '123@gmail.com',
    googleaccount: '有'
  },
  {
    key: 2,
    uid: '000002',
    name: 'Brown',
    phone:'091234567',
    age: 60,
    address: '123@gmail.com',
    googleaccount: '无'
  },
  {
    key: 3,
    uid: '000003',
    name: 'John Brown',
    phone:'091234567',
    age: 60,
    address: '123@gmail.com',
    googleaccount: '无'
  },
  {
    key: 4,
    uid: '000004',
    name: 'Mike Lee',
    phone:'091234567',
    age: 60,
    address: '123@gmail.com',
    googleaccount: '无'
  },
  {
    key: 4,
    uid: '000005',
    name: 'mite',
    phone:'091234567',
    age: 60,
    address: '123@gmail.com',
    googleaccount: '有'
  },
  {
    key: 4,
    uid: '000006',
    name: 'King',
    phone:'091234567',
    age: 60,
    address: '123@gmail.com',
    googleaccount: '有'
  }
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
