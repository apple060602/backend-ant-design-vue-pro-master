<template>
  <div class="center">
    <table>
      <tr>
        <th>币种</th>
        <th>发币数量</th>
        <th>使用者UID</th>
        <th>操作</th>
      </tr>
      <tr>
        <td>
          <a-select default-value="Halo" style="width: 120px" @change="handleChange">
            <a-select-option value="Halo">
              Halo
            </a-select-option>
           </a-select>
        </td>
        <td>
          <a-input-number id="inputNumber" v-model="amount" :min="0" :max="500000" @change="onChange" />
        </td>
        <td>
          <a-select default-value="0001" style="width: 120px" @change="handleChange">
            <a-select-option value="0001">
              0001
            </a-select-option>
          </a-select>
        </td>
        <td>
          <a-button type="primary" @click="submit">
            发送钱
          </a-button>
        </td>
        <td>
          <a-button type="primary" @click="submit2">
            取得钱
          </a-button>
        </td>
        <td>
          <a-button type="primary" @click="submit3">
            取得历史资料
          </a-button>
        </td>
      </tr>
    </table>
  </div>
</template>
<script>
import axios from 'axios';

export default {
  data() {
    return {
      amount: 0,
    };
  },
  methods: {
    // 取得历史纪录
    submit3() {
      let history = axios.get('https://api.105paolian.com/wallet/history/RyAc7Si4rWWuV3TxXu2mqa9jqg1RSbhnRjKWzJ4PiXf6nqSNK');
      console.log(history);
    },
    // 取得钱
    submit2() {
      let accounts = axios.get('https://api.105paolian.com/toychain/accounts/RyAc7Si4rWWuV3TxXu2mqa9jqg1RSbhnRjKWzJ4PiXf6nqSNK');
      console.log(accounts);
    },
    // 发送钱
    submit() {
      const jsonData = JSON.stringify({
        user_id: "0001",
        amount: this.amount
    })
      let res = axios.post('https://api.105paolian.com/wallet/transfers', jsonData);
      let data = this.amount;
      console.log(data);
      console.log(res);
    },
      

    handleChange(value) {
      console.log(`selected ${value}`);
    },
    onChange(value) {
      // console.log('changed', value);
      this.money = value;
    },
  },
};
</script>

<style lang="css">
  .center{
    height: 30vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .aa{
    display: block;
  }
</style>