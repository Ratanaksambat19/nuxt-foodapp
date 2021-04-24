<template>
    <div>
        <label :for="select"> {{ select }} </label>

        <select  :id="select" @change="$emit('change', $event.target.value)">
            <option disabled>--Please select a {{ select }} </option>
            <option v-for="option in selectOptions" :key="option" :value="option"> {{ option }} </option>
        </select>
    </div>
</template>

<script>
    export default {
        props: {
            select: {
                type: String,
                default: "Cusine"
            },
            selectOptions: {
                type: Array,
                default: () => ["tacos", "pizza", "dim sum"]
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>