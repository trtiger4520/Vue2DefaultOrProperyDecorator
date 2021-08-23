<template>
    <div>
        <p>{{name}}</p>
    </div>
</template>

<script lang="ts">
import { Vue, Component, VModel } from 'vue-property-decorator'

// https://github.com/kaorun343/vue-property-decorator#-vmodelpropsargs-propoptions-decorator
@Component
export default class Class_VModel extends Vue {

    // 因使用預設的prop:'value'和回傳事件:'input'，與 @Model 一起用可能有BUG
    @VModel({ type: String }) 
    name!: string;
}
</script>