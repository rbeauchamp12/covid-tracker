<template>
    <div class="grid md:grid-cols-2 gap-4">
        <!--box1 -->
        <div class="shadow-md bg-red-100 p-10 text-center rounded">
            <h3 class="text-3xl text-blue-900 font-bold mb-4">Cases</h3>

            <div class="text-2xl mb-4">
                <span class="font-bold">New:</span>
                {{ numbersWithCommas(stats.NewConfirmed) }}
            </div>
            
            <div class="text-2xl mb-4">
                <span class="font-bold">Total:</span>
                {{ numbersWithCommas(stats.TotalConfirmed) }}
            </div>

        </div> <!-- end of box 1 -->

        <!--box2 -->
        <div class="shadow-md bg-red-200 p-10 text-center rounded">
            <h3 class="text-3xl text-blue-900 font-bold mb-4">Deaths</h3>

            <div class="text-2xl mb-4">
                <span class="font-bold">New:</span>
                {{ numberWithCommas(stats.NewDeaths) }}
            </div>

            
            <div class="text-2xl mb-4">
                <span class="font-bold">Total:</span>
                {{ numbersWithCommas(stats.TotalDeaths) }}
            </div>

        </div> <!-- end of box 2 -->


    </div>
</template>

<script>
export default {
    name: 'DataBoxes',
    props: ['stats'],
    setup () {
        return {
            numberWithCommas (x) {
                return x.toString ()
                .replace(/\B(?=(\d{3})+(?!\d))/g, ',');
            }
        };
    }
};





/*  export default {
    name: 'DataBoxes',
        props: ['stats'],

        methods: {
            numberWithCommas(x) {
                return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',')
            }
        }
    } */

</script>
