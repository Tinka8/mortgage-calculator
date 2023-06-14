<template>
    <div class="bg-gray-100 min-h-screen w-full h-full p-12 text-gray-600">
        <div class="container mx-auto bg-purple-100 shadow-md rounded p-10 m-12">
            <h1 class="font-bold text-3xl pb-10">Mortgage calculator</h1>
            <div class="grid grid-cols-3 gap-10 text-lg">
                <div>
                    <div>Purchase price: <span class="font-semibold text-xl">${{ numbers.purchasePrice }}</span></div>
                    <input v-model="numbers.purchasePrice" type="number" min="100" max="100000" placeholder="315,000" class="w-32 rounded px-2" />
                </div>
                <div>
                    <div>Down payment: <span class="font-semibold text-xl">${{ numbers.downPayment }}</span></div> 
                    <input v-model="numbers.downPayment" type="number" min="100" max="100000" placeholder="315,000" class="w-32 rounded px-2" />
                </div>
                <div>
                    <div>Repayment time: <span class="font-semibold text-xl">{{ numbers.repaymentTime }} years</span></div> 
                    <input v-model="numbers.repaymentTime" placeholder="20" type="range" min="0" max="50" />
                </div>
                <div>
                    <div>Interest rate: <span class="font-semibold text-xl text-black">{{ numbers.interestRate }} %</span></div> 
                    <input v-model="numbers.interestRate" placeholder="10" type="range" min="0" max="20" />
                </div>
                <div>
                    <div>Loan amount</div>
                    <div class="font-semibold text-xl text-black">${{ loanAmount }}</div>
                </div>
                <div>
                    <div>Estimated pr. month:</div>
                    <div class="font-semibold text-xl text-black">${{ estimatedPerMonth.toFixed(2) }}</div>
                </div>
            </div>
            <button class="bg-purple-600 hover:bg-purple-700 shadow-xl text-white text-sm font-bold px-2 py-4 rounded w-1/6 my-8">Get a mortgage quote</button>
        </div>
    </div>
</template>

<script setup> 
import { ref, computed } from 'vue';

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
    vaule.repaymentTime * 12;
});


const estimatedPerMonth = ((interestRateValue * Math.pow(1 + interestRateValue, repaymentTime)) / (Math.pow(1 + interestRateValue, repaymentTime) - 1)) * numbers.purchasePrice;




</script>