<template>
    <div>
        <div id="on"
             @click="switched(true)"
             :class="{active: value}">
            On
        </div>
        <div id="off"
             @click="switched(false)"
             :class="{active: !value}">
            Off
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            value: {
                type: Boolean,
                default: false
            }
        },
        methods: {
            switched(value) {
                this.$emit('input', value);
            }
        }
    }
</script>

<style lang="scss" scoped>
    #on, #off {
        width: 40px;
        height: 20px;
        background-color: #DDDDDD;
        padding: 2px;
        display: inline-block;
        margin: 10px -2px;
        cursor: pointer;
        text-align: center;
    }

    #on:hover, #on.active {
        background-color: #30F2AC;
    }

    #off:hover, #off.active {
        background-color: #F280AC;
    }
</style>