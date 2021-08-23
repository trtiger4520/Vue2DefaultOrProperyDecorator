<template>
    <div>{{text}}</div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator'

@Component
export default class ClassVueComponent extends Vue {
    text: Number = 123
}
</script>