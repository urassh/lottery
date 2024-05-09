<script setup lang="ts">
import type { Lottery } from '~/model/lottery';

const lotteryCollection = useState<Map<number, Lottery>>('lotteryCollection');
const router = useRouter();

const lotteryNumber = ref<number>(0);

const drawLottery = () => {
    const randomNumber = Math.floor(Math.random() * 100) + 1;
    lotteryNumber.value = randomNumber;
};

const storeLotteryCollection = () => {
    lotteryCollection.value.set(lotteryNumber.value, { id: `${lotteryNumber.value}`, number: lotteryNumber.value });
};

const toIndex = () => {
    router.push({ name: 'index' });
};

const indexButtonTapped = () => {
    storeLotteryCollection();
    toIndex();
};

drawLottery();
</script>

<template>
    <h2>{{ lotteryNumber }}</h2>
    <button v-on:click = "indexButtonTapped">リストへ戻る</button>
</template>
