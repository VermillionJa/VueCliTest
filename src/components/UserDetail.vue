<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User Name: {{reverseName()}}</p>
        <button @click="resetName">Reset Name</button>
        <button @click="resetFunction()">Reset Name (Callback)</button>
    </div>
</template>

<script>
    export default {
        props: {
            userName: {
                type: String,
                required: true,
            },
            resetFunction: Function
        },
        methods: {
            reverseName() {
                return this.userName.split("").reverse().join("");
            },
            resetName() {
                this.userName = "Jake";
                this.$emit("nameWasReset", this.userName);
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
