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
          <a-input-number id="inputNumber" v-model="value" :min="0" :max="500000" @change="onChange" />
        </td>
        <td>
          <a-select default-value="0001" style="width: 120px" @change="handleChange">
            <a-select-option value="0001">
              0001
            </a-select-option>
          </a-select>
        </td>
        <td>
          <a-button type="primary">
            发送
          </a-button>
        </td>
      </tr>
    </table>
  </div>
</template>
<script>
export default {
  data() {
    return {
      value: 0,
    };
  },
  methods: {
    handleChange(value) {
      console.log(`selected ${value}`);
    },
    onChange(value) {
      console.log('changed', value);
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