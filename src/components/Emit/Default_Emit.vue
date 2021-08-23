<template>
    <div>
        <button @click="clickBtn">Class_Emit：回應事件</button>
        <button @click="clickBtnWithParam">Class_Emit：回應事件並傳遞參數</button>
    </div>
</template>

<script>
export default {
    name: 'Default_Emit',
    methods: {
        clickBtn() {
            this.$emit('click');
        },
        clickBtnWithParam() {
            this.$emit('click2', "Class_Emit param");    
        }
    },
}
</script>