<template>
    <div class="brick" style="height: 335.656px;">
        <div class="brick__inner">
            <div class="brick__image">
                <div class="brick__image-inner " :style="`background-image: url('${talk.picture}');`"></div>
                <div data-detail="https://slides.com/aurelienloyer/handson-vuejs" class="brick__hover ">
                    <div class="brick__hover-action-wrap">
                        <a href="https://slides.com/aurelienloyer/handson-vuejs" target="_blank" class="brick__hover-action icon-icon-external">
                            Goto Website
                        </a>
                    </div>
                </div>
            </div>
            <div class="brick__caption">
                <div class="brick__caption-upper">
                    <a target="_blank" :href="talk.slide" class="brick__title">
                        {{ talk.name }}
                    </a>
                    <span class="brick__tagline">
                        {{ talk.description }}
                    </span>
                    <ul class="brick__sessions" v-if="talk.sessions">
                        <li v-for="session in talk.sessions">{{ session }}</li>
                    </ul>
                </div>
                <div class="brick__caption-lower">
                    <div class="pull-left">
                        <a v-for="tag in talk.hashtag">#{{ tag }} </a>
                    </div>
                    <div class="pull-right">
                        <i class="far fa-eye"></i> {{ talk.view }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
    export default {
        props: [
            'talk'
        ]
    }
</script>

<style scoped>

</style>
