<script>
export default {
    methods: {
        handleClick() {
        this.$emit('buttonClick');
        },
    },   
}
</script>

<template>
            <div @click="handleClick" style="width: 30px; height: 30px; background-color: red; cursor: pointer;">
            <p>macron config</p>
        </div>
    
</template>