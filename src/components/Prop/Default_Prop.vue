<template>
    <div>
        <h3>Def_Prop</h3>
        <p>property1: {{property1}}</p>
        <p>property2: {{property2}}</p>
        <p>property3: {{property3}}</p>
        <p>propsync1: {{propsync1}}</p>
    </div>
</template>

<script>
export default {
    name: 'Default_Prop',
    props: {
        property1: String,
        property2: {
            required: true,
            type: String
        },
        property3: {
            type: String,
            default: ''
        },
        propsync1: String
    },
    computed: {
        syncedName: {
            get() {
                return this.propsync1
            },
            set(value) {
                this.$emit('update:propsync1', value)
            },
        },
    },
}
</script>