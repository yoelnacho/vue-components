<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <p :class="$style.a">Testing</p>
        <p :class="{ [$style.foo]: isRed }">
            Am I red?
        </p>
        <p :class="[$style.foo, $style.bar]">
            Red and bold
        </p>
    </div>
</template>

<script>
export default {
    name: 'HelloWorld',
    props: {
        msg: String
    },
    data() {
        return {
            isRed: {
                type: String,
                value: true
            }
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style module>
/*  HELLO COMPONENT */
h3 {
    margin: 40px 0 0;
}
ul {
    list-style-type: none;
    padding: 0;
}
li {
    display: inline-block;
    margin: 0 10px;
}
.foo {
    composes: red from "../assets/scss/main.scss";
}

.bar {
    composes: red from "../assets/scss/main.scss";
    composes: bold from "../assets/scss/main.scss";
}
</style>
