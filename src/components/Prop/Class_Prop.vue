<template>
    <div>
        <h3>Class_Prop</h3>
        <p>property1: {{property1}}</p>
        <p>property2: {{property2}}</p>
        <p>property3: {{property3}}</p>
        <p>propsync1: {{propsync1}}</p>
    </div>
</template>

<script lang="ts">
import { Vue, Component, Prop, PropSync } from 'vue-property-decorator'
// https://github.com/kaorun343/vue-property-decorator#-propsyncpropname-string-options-propoptions--constructor--constructor---decorator
@Component
export default class Class_Prop extends Vue {
    @Prop(String)
    property1!: string;

    @Prop({
        type: String,
        required: true
    })
    property2!: string;

    @Prop({
        type: String,
        default: ''
    })
    property3!: string;

    // https://github.com/kaorun343/vue-property-decorator#-propsyncpropname-string-options-propoptions--constructor--constructor---decorator
    @PropSync('propsync1', {
        type: String
    })
    propsync11!: String; // 不可與實際的prop相同名稱.. data 會與 computed 的 set屬性 相衝
}
</script>