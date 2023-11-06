<template>
    <div class="table-responsive">
      <table class="table table-striped table-bordered table-hover">
        <thead class="table-dark">
          <tr>
            <th>base</th>
            <th>quote</th>
            <th>Last Price</th>
            <th>Change</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(item, key) in binanceData" :key="key">
            <td>{{ item.base }}</td>
            <td>{{ item.quote }}</td>
            <td>{{ item.last }}</td>
            <td>{{ item.change }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </template>

  <script>
  export default {
    data() {
      return {
        binanceData: {}
      };
    },
    mounted() {
      const socket = new WebSocket('wss://qeshmex.com:1011/');
      socket.onmessage = (event) => {
        const data = JSON.parse(event.data);
        if (data && data.binance) {
          this.binanceData = data.binance;
        }
      };
    }
  };
  </script>

  <style scoped>
  /* Your scoped styles go here */
  </style>
