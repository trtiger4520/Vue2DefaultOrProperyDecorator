<template>
    <div>
        <p>tprovide Provide: {{tprovide}}</p>
        <p>tprovide2 Provide: {{tprovide2}}</p>
        <DefaultProvideChild />
    </div>
</template>

<script>
import DefaultProvideChild from './Default_Provide_Child.vue'

export default {
    name: 'Default_Provide',
    components: {
        DefaultProvideChild,
    },
    data() {
        return {
            tprovide: '685',
            tprovide2: '784',
        }
    },
    provide() {
        return {
            tprovide: this.tprovide,
            tprovide2: this.tprovide2,
        }
    }
}
</script>