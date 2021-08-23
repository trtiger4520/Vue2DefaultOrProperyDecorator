<template>
    <div>
        <button @click="clickBtn">Class_Emit：回應事件</button>
        <button @click="clickBtnWithParam">Class_Emit：回應事件並傳遞參數</button>
    </div>
</template>

<script lang="ts">
import { Vue, Component, Emit } from 'vue-property-decorator'
// https://github.com/kaorun343/vue-property-decorator#Emit
@Component
export default class Class_Emit extends Vue {
    @Emit('click')
    clickBtn() {}
    @Emit('click2') // 可以使用自訂事件
    clickBtnWithParam() { return "Class_Emit param"; }
}
</script>