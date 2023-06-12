<template>
    <div class="bg-gray-100 min-h-screen w-full h-full p-12">
        <div class="container mx-auto bg-purple-100 shadow-md rounded p-10 m-12">
            <h1 class="font-bold text-xl pb-10">Mortgage calculator</h1>
            <div class="grid grid-cols-3 gap-10 text-lg">
                <div>
                    <div>Purchase price: <span class="font-semibold text-xl">${{ purchasePrice }}</span></div>
                    <input v-model="purchasePrice" placeholder="Purchase Price" />
                </div>
                <div>
                    <div>Down payment: <span class="font-semibold text-xl">${{ downPayment }}</span></div> 
                    <input v-model="downPayment" placeholder="Down Payment" />
                </div>
                <div>
                    <div>Repayment time: <span class="font-semibold text-xl">{{ repaymentTime }} years</span></div> 
                    <input v-model="repaymentTime" placeholder="Repayment Time" />
                </div>
                <div class="flex items-center">
                    <div>Interest rate:</div> 
                    <div class="font-semibold text-xl">3%</div>
                    <div></div>
                </div>
                <div>
                    <div>Loan amount</div>
                    <div class="font-semibold text-xl"> $315,000</div>
                </div>
                <div>
                    <div>Estimated pr. month:</div>
                    <div class="font-semibold text-xl">$1,300</div>
                </div>
            </div>
            <button class="bg-purple-600 hover:bg-purple-700 shadow-xl text-white text-sm font-bold px-2 py-4 rounded w-1/6 my-8">Get a mortgage quote</button>
        </div>
    </div>
</template>

<script setup> 
import { ref } from 'vue';

const numebrs = ref({
    purchasePrice: "",
    downPayment: "",
    repaymentTime: "",
    interestRate: ""
});



</script>