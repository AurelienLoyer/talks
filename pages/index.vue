<template>
    <section id="main">
        <h1>Talks</h1>
        <section class="bricks">
            <v-talk v-for="(talk,index) in talks" :key="`talk-${index}`" :talk="talk"></v-talk>
        </section>
    </section>
</template>

<script>

    import talks from '../talks.json'
    import Talk from '../components/Talk'

    export default {
        data() {
            return {
                talks,
            }
        },
        components: {
            'v-talk': Talk,
        },
        created() {
        },
    }
</script>

<style scoped>
    #main {
        max-width: 1200px;
        margin: 50px auto;
    }

    .bricks{
        padding: 1%;
    }
</style>
