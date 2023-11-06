<template>
    <div class="table-responsive">
      <table class="table table-bordered table-hover">
        <thead class="table-dark">
          <tr>
            <th>base</th>
            <th>quote</th>
            <th>Last Price</th>
            <th>Change</th>
          </tr>
        </thead>
        <tbody v-if="Object.keys(binanceData).length > 0">
            <tr v-for="(item, key) in binanceData" :key="key">
                <td>{{ item.base }}</td>
                <td>{{ item.quote }}</td>
                <td>{{ item.last }}</td>
                <td>{{ item.change }}</td>
            </tr>
        </tbody>
        <tbody v-else class="placeholder-glow">
            <tr>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
            </tr>
            <tr>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
            </tr>
            <tr>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
            </tr>
            <tr>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
            </tr>
            <tr>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
                <td><span class="placeholder w-100 p-3 bg-secondary"></span></td>
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
