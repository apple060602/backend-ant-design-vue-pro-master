<template>
    <table class="table table-hover">
      <tr>
        <th>币种</th>
        <th>类别</th>
        <th>数量</th>
        <th>转账类型</th>
        <th>UID</th>
      </tr>
      <tr v-for="li in list" :key="li">
        <td v-text="li.currency"></td>
        <td v-text="li.updom"></td>
        <td v-text="li.amount"></td>
        <td v-text="li.transfertype"></td>
        <td v-text="li.uid"></td>
      </tr>
    </table>
</template>

<script>
import axios from 'axios';
  export default {
    data () {
      return {
          list: [],
      }
    },
    mounted() {
      axios.get("https://api.105paolian.com/wallet/history/RyAc7Si4rWWuV3TxXu2mqa9jqg1RSbhnRjKWzJ4PiXf6nqSNK")
        .then(response => {
            console.log(response.data);
           
          response.data.forEach(obj => {
            obj.currency = 'halo';
            obj.updom = '转出';
            obj.transfertype = '外转';
            obj.uid = '0001';
        });
         this.list = response.data;
      })
  }
}
</script>
<style lang="css">
  .table{
    display: inline-block;
    justify-content: center;
    align-items: center;
  }
  .table th{
    font-size: 18px;
  }
  .table tr{
    border: 1px solid #000;
  }
  .table td{
    font-size: 16px;
    width: 1000px;
  }
</style>