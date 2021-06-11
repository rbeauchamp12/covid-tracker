<template>
    <select @change="onChange()" v-modal="selected" class="form-select mt-10 block w-full border p-3 rounded">
        <option value="0"> Select Country </option>

        <option v-for ="country in countries" :value="country.ID"> {{ country.Country }} </option>

    </select>
</template>

<script>
import {ref} from 'vue';

export default {
    name: 'CountrySelect',
    props: ['countries'],
    setup ({ countries }, { emit }) {
        const selected = ref(0);

        return {
            selected,
            onChange () {
                const country = countries.find((item) => item.ID === selected.value);
                emit('get-country', country);
            }
        };
    }
   /* data() {
        return {
            select: 0
        }
    },

    methods: {
        onChange() {
            const country = this.countries.find((item) =>item.ID === this.selected)

            this.$emit('get-country', country)
        },
    }, */
};
</script>
