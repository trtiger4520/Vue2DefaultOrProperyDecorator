<template>
    <div>child</div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'

@Component
export default class Class_Ref_Child extends Vue {
    text: string = '5555';
}
</script>