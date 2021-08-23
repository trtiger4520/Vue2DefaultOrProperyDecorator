<template>
    <div>
        <h3>Def_Prop</h3>
        <p>context1: {{context1}}</p>
    </div>
</template>

<script>
export default {
    name: 'Default_Model',
    model: {
        prop: 'context1',
        event: 'input1',
    },
    props: {
        context1: {
            type: String,
            required: true
        },
        checked: {
            type: Boolean,
        },
    },
    computed: {
        checkedValue: {
            get() {
                return this.checked
            },
            set(value) {
                this.$emit('input1', value)
            },
        },
    },
}
</script>