<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User Name: {{reverseName()}}</p>
        <button @click="resetName">Reset Name</button>
    </div>
</template>

<script>
    export default {
        props: {
            connectionName: [String, Array],
            userName: {
                type: String,
                required: true,
            },
            maxConnectionCount: {
                type: Number,
                default: 100
            },
            config: {
                type: Object,
                default() {
                    return {
                        serverId: 0,
                        serverName: "100s-54hd"
                    }
                }
            }
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
