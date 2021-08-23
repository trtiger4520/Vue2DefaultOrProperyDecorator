<template>
    <div>
        <p>tprovide Provide: {{tprovide}}</p>
        <p>tprovide2 Provide: {{tprovide2}}</p>
        <ClassProvideChild />
    </div>
</template>

<script lang="ts">
import { Vue, Component, Provide, ProvideReactive } from 'vue-property-decorator'
import ClassProvideChild from './Class_Provide_Child.vue'

// https://github.com/kaorun343/vue-property-decorator#-propsyncpropname-string-options-propoptions--constructor--constructor---decorator
@Component({
    components: {
        ClassProvideChild
    }
})
export default class Class_Provide_Parent extends Vue {
    @Provide('tprovide')
    tprovide: string = '213';
    @Provide('tprovide2')
    tprovide2: string = '213';

    // 可以即時反應的版本 (沒有一般作法)
    @ProvideReactive() 
    two = 'value';
}
</script>