<template>
    <div class="bg-gray-100 min-h-screen w-full h-full p-12">
        <div class="container mx-auto bg-purple-100 shadow-md rounded p-10 m-12">
            <h1 class="font-bold text-xl pb-10">Mortgage calculator</h1>
            <div class="grid gap-y-72 grid-cols-3 text-lg">
                <div class="flex items-center">
                    <div>Purchase price:</div>
                    <div class="font-semibold text-lg">$450,000</div>
                    <div></div>
                </div>
                <div class="flex items-center">
                    <div>Down payment:</div> 
                    <div class="font-semibold text-lg">$135,000</div>
                    <div></div>
                </div>
                <div class="flex items-center">
                    <div>Repayment time:</div> 
                    <div class="font-semibold text-lg">25 years</div>
                    <div></div>
                </div>
                <div class="flex items-center">
                    <div>Interest rate:</div> 
                    <div class="font-semibold text-lg">3%</div>
                    <div></div>
                </div>
                <div>
                    <div>Loan amount</div>
                    <div class="font-semibold text-lg"> $315,000</div>
                </div>
                <div>
                    <div>Estimated pr. month:</div>
                    <div class="font-semibold text-lg">$1,300</div>
                </div>
            </div>
            <button class="bg-purple-600 hover:bg-purple-700 shadow-xl text-white text-sm font-bold px-2 py-2 rounded w-1/6 my-8">Get a mortgage quote</button>
        </div>
    </div>
</template>

<script setup> 
</script>