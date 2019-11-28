<template>
    <div>
        <h1>User with dynamic pathing. ID of {{ $route.params.id }}</h1>
    </div>
</template>

<script>
    export default {
        // Special property by Nuxt.
        validate(data) {          
            return /^\d+$/.test(data.params.id);
        },

        // Special property by Nuxt.
        layout: 'users'
    }
</script>

<style lang="scss" scoped>

</style>