<template>
    <div>
        <p>{{name}}</p>
    </div>
</template>

<script>
export default {
    name: 'Default_VModel',
    props: {
        value: { // v-model 預設要件(1)
            type: String,
        },
    },
    computed: {
        name: { // 自訂屬性名稱
            get() {
                return this.value
            },
            set(value) {
                this.$emit('input', value) // v-model 預設要件(2)
            },
        },
    },
}
</script>