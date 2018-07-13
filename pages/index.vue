<template>
    <section>
        <h1>Talks</h1>

        <section class="bricks">

            <v-talk></v-talk>

        </section>
    </section>
</template>

<script>

    import talks from '../talks.json'
    import Talk from '../components/Talk'

    export default {
        data() {
            return {

            }
        },
        components: {
            'v-talk': Talk,
        },
        created() {
            console.log(talks);
        },
    }
</script>

<style scoped>
</style>
