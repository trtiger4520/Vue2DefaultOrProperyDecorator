<template>
    <div>
        <input type="text" v-model="name">
        <p>name: {{name}}</p>
    </div>
</template>

<script>
export default {
    name: 'Default_Watch',
    data() {
        return {
            name: 'string'
        }
    },
    watch: {
        'name'(val, prev) {
            console.log(val, prev);
        }
    }
}
</script>