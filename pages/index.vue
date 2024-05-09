<script setup lang="ts">
import type { Lottery } from '~/model/lottery';

const router = useRouter();
const lotteryCollection = useState<Map<number, Lottery>>('lotteryCollection');

const toDrowView = () => {
    router.push({ name: 'drawLottery' });
};

</script>

<template>
    <main>
        <h2>抽選リスト</h2>

        <ul>
            <li
                v-for="[id, lottery] in lotteryCollection"
                v-bind:key="id"
            >{{ lottery.number }}</li>
        </ul>

        <button
            v-on:click="toDrowView"
        >抽選を引く</button>
    </main>
</template>
