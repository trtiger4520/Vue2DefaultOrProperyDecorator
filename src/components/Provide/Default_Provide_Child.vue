<template>
    <div>
        <p>tprovide Inject: {{ tprovide }}</p>
        <p>tprovide Inject: {{ tprovide2 }}</p>
    </div>
</template>

<script>
export default {
    name: 'Default_Provide_Child',
    inject: {
        tprovide: 'tprovide',
        tprovide2: 'tprovide2',
    }
}
</script>