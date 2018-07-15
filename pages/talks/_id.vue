<template>
    <div>
        {{talk}}
    </div>
</template>

<script>
    import talks from '../../talks.json';

    export default {
        data() {
            return {
                talk: {}
            }
        },
        created() {
            this.talk = talks.find(talk => talk.uname === this.$route.params.id)
            console.log(this.talk)
        },
    }
</script>

<style lang="scss">

</style>
