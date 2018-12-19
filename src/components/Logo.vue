<template>
    <div class="hello">
        <p :class="$style.color">logo</p>
    </div>
</template>

<script>
export default {
    name: 'Logo'
}
</script>

<style module>
    .text {
        font-weight: bold;
    }

    .color {
        color: green
    }
</style>
