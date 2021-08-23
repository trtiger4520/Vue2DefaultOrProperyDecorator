<template>
    <div>
        <input type="text" v-model="name">
        <p>name: {{name}}</p>
    </div>
</template>

<script lang="ts">
import { Vue, Component, Watch } from 'vue-property-decorator'
// https://github.com/kaorun343/vue-property-decorator#-propsyncpropname-string-options-propoptions--constructor--constructor---decorator
@Component
export default class Class_Watch extends Vue {
    name: string = 'string';

    @Watch('name')
    fn(val: string, prev: string) {
        console.log(val, prev);
    }
}
</script>