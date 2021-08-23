<template>
    <div>
        <p>tprovide Inject: {{ tprovide }}</p>
        <p>tprovide Inject: {{ tprovide2 }}</p>
    </div>
</template>

<script lang="ts">
import { Vue, Component, Inject, InjectReactive } from 'vue-property-decorator'

@Component
export default class Class_Provide_Child extends Vue {
    @Inject()
    tprovide!: string;
    @Inject({
        from: 'tprovide2',
        default: 'def'
    })
    tprovide2!: string;

    // 自動更新父組件調整的值
    @InjectReactive() 
    two!: string;
}
</script>