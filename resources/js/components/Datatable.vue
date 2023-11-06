<template>
    <div class="table-responsive">
        <table class="table table-bordered table-hover">
            <thead class="table-dark">
                <tr>
                    <th>Coin</th>
                    <th>Last Price</th>
                    <th>Change Percent</th>
                    <th>High</th>
                    <th>Low</th>
                    <th>Volume</th>
                    <th>Link</th>
                </tr>
            </thead>
            <tbody v-if="Object.keys(binanceData).length > 0">
                <tr v-for="(item, key) in binanceData" :key="key">
                    <td>
                        <div class="d-flex">
                            <img
                                loading="lazy"
                                :src="`https://qeshmex.com/storage/images/coin-icons/__${item.quote}.png`"
                                height="40"
                                width="40"
                                class="p-1"
                            />
                            <div class="text-center">
                                <span class="d-block">{{item.quote}}</span>
                                <span class="d-block">{{item.base}}</span>
                            </div>
                        </div>
                    </td>
                    <td :data-last-price="item.last" :data-key="key">
                        {{ Number(item.last) }}
                    </td>
                    <td
                        :class="
                            item.changePercent > 0
                                ? 'text-success'
                                : 'text-danger'
                        "
                    >
                        {{ Number(item.changePercent).toFixed(2) }}
                    </td>
                    <td class="text-success">
                        {{ Number(item.high).toFixed(0) }}
                    </td>
                    <td class="text-danger">
                        {{ Number(item.low).toFixed(0) }}
                    </td>
                    <td>{{ Number(item.quoteVolume).toFixed(0) }}</td>
                    <td><a href="#" class="btn">Buy/Sell</a></td>
                </tr>
            </tbody>
            <tbody v-else class="placeholder-glow">
                <tr>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                </tr>
                <tr>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                </tr>
                <tr>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                </tr>
                <tr>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                </tr>
                <tr>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                    <td>
                        <span class="placeholder w-100 p-3 bg-secondary"></span>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    data() {
        return {
            binanceData: {},
        };
    },
    methods: {
        updateClassBasedOnPrice() {
            const tdElements = document.querySelectorAll("[data-last-price]");
            tdElements.forEach((td) => {
                const lastPrice = parseFloat(
                    td.getAttribute("data-last-price")
                );
                const key = td.getAttribute("data-key");
                const currentPrice = this.binanceData[key]?.last;
                if (!isNaN(lastPrice) && !isNaN(currentPrice)) {
                    if (currentPrice >= lastPrice) {
                        td.classList.add("text-success");
                        td.classList.remove("text-danger");
                    } else if (currentPrice < lastPrice) {
                        td.classList.add("text-danger");
                        td.classList.remove("text-success");
                    }
                }
            });
        },
    },
    mounted() {
        const socket = new WebSocket("wss://qeshmex.com:1011/");
        socket.onmessage = (event) => {
            const data = JSON.parse(event.data);
            if (data && data.binance) {
                this.binanceData = data.binance;
                this.updateClassBasedOnPrice();
            }
        };
    },
};
</script>

<style scoped>
.green {
    color: green;
}

.red {
    color: red;
}
</style>
