<template>
    <div>
        <p>子組件內容：{{childText}}</p>
        <ClassRefChild ref="RefName" />
    </div>
</template>

<script lang="ts">
import { Vue, Component, Ref } from 'vue-property-decorator'
import ClassRefChild from './Class_Ref_Child.vue'

// https://github.com/kaorun343/vue-property-decorator#-propsyncpropname-string-options-propoptions--constructor--constructor---decorator
@Component({
    components: {
        ClassRefChild
    }
})
export default class Class_Ref_Parent extends Vue {
    @Ref('RefName')
    childNode?: ClassRefChild; // 使用VueDev工具查看值

    childText: string = '';

    mounted() {
        this.childText = this.childNode?.text || '未取得 ref 元件內容';
    }
}
</script>