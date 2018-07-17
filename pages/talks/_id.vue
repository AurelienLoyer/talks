<template>
    <div>
        <div class="brick__container" v-if="talk.name">
            <div class="detail__left">
                <div class="detail__picture" style="background-image: '/default_picture.jpg'" alt=""></div>
            </div>
            <div class="detail__right">
                <div class="detail-info">
                    <div class="content__block">
                        <h1>{{ talk.name }}</h1>
                        <hr>
                        <blockquote>{{ talk.description }}</blockquote>
                        <dl>
                            <dt>Slide:</dt>
                            <dd>
                                <a :href="talk.slide" target="_blank">{{cleanUrl(talk.slide)}}</a>
                            </dd>
                            <template v-if="talk.github">
                                <dt>Github:</dt>
                                <dd>
                                    <a :href="talk.github" target="_blank" class="brick__twitter">{{cleanUrl(talk.github)}}</a>
                                </dd>
                            </template>
                        </dl>
                        <hr>
                    </div>
                    <div class="detail-info__buttons">
                        <a :href="talk.slide" target="_blank" class="button--bold">
                            View Slide
                        </a>
                        <a href="https://twitter.com/home?status="
                            target="_blank" class="button--outlined">Tweet This</a>
                    </div>
                    <br>
                    <br>
                    <div id="js-carbon-container" class="carbon-ad--detail"></div>
                </div>
            </div>
        </div>
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
        mounted() {
            this.talk = talks.find(talk => talk.uname === this.$route.params.id)
            console.log(this.talk)
        },
        methods: {
            cleanUrl(url) {
                return url;
            },
        }
    }
</script>

<style lang="scss">
    .brick__container {
        max-width: 90%;
        margin: 50px auto;
        display: flex;
        justify-content: space-between;
        color: #435b71;
    }

    .detail__left {
        min-width: 66.66666667%;
        border-radius: 20px;
        margin-right: 50px;
        overflow: hidden;
        background-color: #fff;
        -webkit-transition: all .2s ease-out;
        transition: all .2s ease-out;
        -webkit-box-shadow: 0 2px 43px -4px rgba(0, 0, 0, .19);
        box-shadow: 0 2px 43px -4px rgba(0, 0, 0, .19);
    }

    .content__block h1 {
        font-size: 36px;
        font-weight: 700;
    }

    blockquote {
        padding: 11px 22px;
        margin: 0 0 22px;
        font-size: 20px;
        border-left: 5px solid #eee;
    }

    .content__block blockquote {
        font-size: 19px;
        padding-right: 0;
    }

    .detail-info dl {
        display: block;
        margin-top: 20px;
    }

    .detail-info dl dt {
        float: left;
        clear: left;
        font-weight: 700;
        margin-right: 5px;
        margin-bottom: 5px;
    }

    .detail-info dl dd {
        overflow: hidden;
        margin-bottom: 5px;
    }

    .content__block a {
        -ms-word-break: break-all;
        word-break: break-all;
        word-break: break-word;
        -webkit-hyphens: auto;
        -ms-hyphens: auto;
        hyphens: auto;
        color: #40b883;
        font-weight: 700;
    }

    .detail-info__buttons {
        margin-top: 15px;
    }

    .button--bold {
        display: inline-block;
        border-radius: 27px;
        padding: 16px 27px;
        font-size: 14px;
        line-height: 17px;
        font-weight: 700;
        text-transform: uppercase;
        -webkit-transition: all .2s ease-out;
        transition: all .2s ease-out;
        border: 3px solid #40b883;
        background-color: #40b883;
        color: #fff;
    }

    .button--outlined {
        display: inline-block;
        border-radius: 27px;
        padding: 16px 27px;
        font-size: 14px;
        line-height: 17px;
        font-weight: 700;
        text-transform: uppercase;
        -webkit-transition: all .2s ease-out;
        transition: all .2s ease-out;
        border: 3px solid #40b883;
        background-color: #fff;
        color: #40b883;
    }
</style>
