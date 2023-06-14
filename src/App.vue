<template>
    <div class="w-full h-full min-h-screen p-12 text-gray-600 bg-gray-100">
        <div class="container p-10 m-12 mx-auto bg-purple-100 rounded shadow-md">
            <h1 class="pb-10 text-3xl font-bold">Mortgage calculator</h1>
            <div class="grid grid-cols-3 gap-10 text-lg">
                <div>
                    <div>
                        Purchase price:
                        <span class="text-xl font-semibold">${{ numbers.purchasePrice }}</span>
                    </div>
                    <input v-model="numbers.purchasePrice" type="number" min="100" max="100000" placeholder="315,000"
                        class="w-32 px-2 rounded" />
                </div>
                <div>
                    <div>
                        Down payment:
                        <span class="text-xl font-semibold">${{ numbers.downPayment }}</span>
                    </div>
                    <input v-model="numbers.downPayment" type="number" min="100" max="100000" placeholder="315,000"
                        class="w-32 px-2 rounded" />
                </div>
                <div>
                    <div>
                        Repayment time:
                        <span class="text-xl font-semibold">{{ numbers.repaymentTime }} years</span>
                    </div>
                    <input v-model="numbers.repaymentTime" placeholder="20" type="range" min="0" max="50" />
                </div>
                <div>
                    <div>
                        Interest rate:
                        <span class="text-xl font-semibold text-black">{{ numbers.interestRate }} %</span>
                    </div>
                    <input v-model="numbers.interestRate" placeholder="10" type="range" min="0" max="20" />
                </div>
                <div>
                    <div>Loan amount</div>
                    <div class="text-xl font-semibold text-black">${{ loanAmount }}</div>
                </div>
                <div>
                    <div>Estimated pr. month:</div>
                    <div class="text-xl font-semibold text-black">
                        ${{ estimatedPerMonth.toFixed(2) }}
                    </div>
                </div>
            </div>
            <button
                class="w-1/6 px-2 py-4 my-8 text-sm font-bold text-white bg-purple-600 rounded shadow-xl hover:bg-purple-700">
                Get a mortgage quote
            </button>
        </div>
    </div>
</template>

<script setup>
import { ref, computed } from "vue";

const numbers = ref({
    purchasePrice: "",
    downPayment: "",
    repaymentTime: "",
    interestRate: "",
});

const loanAmount = computed(() => {
    return numbers.value.purchasePrice - numbers.value.downPayment;
});

const interestRateValue = computed(() => {
    return numbers.value.interestRate / 100 / 12;
});

const repaymentTime = computed(() => {
    return numbers.value.repaymentTime * 12;
});

const estimatedPerMonth = computed(() => {
    return (
        ((interestRateValue.value *
            Math.pow(1 + interestRateValue.value, repaymentTime.value)) /
            (Math.pow(1 + interestRateValue.value, repaymentTime.value) - 1)) *
        numbers.value.purchasePrice
    );
});
</script>