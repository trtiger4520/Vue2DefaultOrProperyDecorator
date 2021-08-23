<template>
    <div>
        <p>子組件內容：{{childText}}</p>
        <ClassRefChild ref="RefName" />
    </div>
</template>

<script>
import ClassRefChild from './Default_Ref_Child.vue'

export default {
    name: 'Default_Provide',
    components: {
        ClassRefChild,
    },
    data() {
        return {
            childText: '',
        }
    },
    mounted() {
        const childNode = this.$refs['RefName'];
        this.childText = childNode?.text || '未取得 ref 元件內容';
    }
}
</script>