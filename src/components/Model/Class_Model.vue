<template>
    <div>
        <p>context: {{context1}}</p>
    </div>
</template>

<script lang="ts">
import { Vue, Component, Model, Prop } from 'vue-property-decorator'
// https://github.com/kaorun343/vue-property-decorator#Model
@Component
export default class Class_Model extends Vue {
    // model + prop
    @Model('input1', {
        type: String,
        required: true
    })
    context1!: string;

    // model + prop sync (model 設定只有一組，多次使用可能會被覆蓋)
    // @ModelSync('checked', 'change', { type: Boolean })
    // readonly checkedValue!: boolean
}

// 目前個人認為 Model、ModelSync 不太需要用到，
// 只需要自訂 @Component 裡面的設定值即可
// 屬性用 Prop、PropSync 取代
@Component({
    model: {
        prop: 'context1',
        event: 'change',
    }
})
export class Class_Model_Other extends Vue {
    // prop
    @Prop({
        type: String,
        required: true
    })
    context1!: string;
}
</script>