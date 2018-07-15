<template>
    <div class="brick" style="height: 335.656px;">
        <div class="brick__inner">
            <div class="brick__image">
                <nuxt-link :to="'talks/' + talk.uname ">
                    <div class="brick__image-inner " :style="`background-image: url('${talk.picture}');`"></div>
                </nuxt-link>
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
    .brick {
        position: relative;
        min-height: 1px;
        padding-left: 25px;
        padding-right: 25px;
    }

    @media (min-width: 768px) {
        .brick {
            float: left;
            width: 50%;
        }
    }

    @media (min-width: 768px) {
        .brick {
            position: relative;
            min-height: 1px;
            padding-left: 25px;
            padding-right: 25px;
        }
    }

    .brick {
        margin-bottom: 50px;
        position: relative;
        float: left;
        width: 100%;
        min-height: 1px;
        padding-left: 25px;
        padding-right: 25px;
    }

    *,
    :after,
    :before {
        -webkit-box-sizing: border-box;
        box-sizing: border-box;
    }

    @media (min-width: 992px) {
        .brick {
            float: left;
            width: 33.33333333%;
        }
    }

    .brick__inner {
        border-radius: 20px;
        overflow: hidden;
        background-color: #fff;
        width: 100%;
        -webkit-transition: all 0.2s ease-out;
        transition: all 0.2s ease-out;
        -webkit-box-shadow: 0 2px 43px -4px rgba(0, 0, 0, 0.19);
        box-shadow: 0 2px 43px -4px rgba(0, 0, 0, 0.19);
    }

    .brick__image {
        overflow: hidden;
        cursor: pointer;
        position: relative;
        padding-top: 66.17647059%;
    }

    .brick__image-inner {
        -webkit-transition: all 0.3s;
        transition: all 0.3s;
        width: 100%;
        height: 100%;
        position: absolute;
        top: 0;
        left: 0;
        background-repeat: no-repeat;
        background-position: 50%;
        background-size: cover;
        background-size: 100% auto;
        border-top-right-radius: 20px;
        border-top-left-radius: 20px;
    }

    .brick__hover {
        -webkit-transition: all 0.3s ease-in-out;
        transition: all 0.3s ease-in-out;
        opacity: 0;
        filter: alpha(opacity=0);
        background-color: rgba(67, 91, 113, 0.5);
        position: absolute;
        top: 100%;
        left: 0;
        height: 100%;
        width: 100%;
    }

    .brick__hover-action-wrap {
        position: absolute;
        top: 0;
        left: 0;
        padding: 8px;
        background-color: hsla(0, 0%, 100%, 0.7);
        top: 50%;
        left: 50%;
        -webkit-transform: translate(-50%, -50%);
        transform: translate(-50%, -50%);
        border-radius: 38px;
        white-space: nowrap;
        min-width: 156px;
    }

    .brick__hover-action {
        color: #fff;
        background-color: #435b71;
        border-radius: 100%;
        display: block;
        margin-left: 5px;
        margin-right: 5px;
        float: left;
        height: 60px;
        width: 60px;
        background-position: 50%;
        overflow: hidden;
        text-indent: -9999px;
        -webkit-transition: all 0.2s ease-out;
        transition: all 0.2s ease-out;
        cursor: pointer;
    }

    .icon-icon-external {
        background-image: url(data:image/svg+xml;charset=US-ASCII,%3C%3Fxml%20version%3D%221.0%22%20encod…%3E%0A%20%20%20%20%20%20%20%20%3C/g%3E%0A%20%20%20%20%3C/g%3E%0A%3C/svg%3E);
        background-repeat: no-repeat;
    }


    .brick__caption {
        background-color: #fff;
        position: relative;
        border-bottom-right-radius: 20px;
        border-bottom-left-radius: 20px;
    }

    .brick__title {
        font-size: 24px;
        font-weight: 700;
        line-height: 27px;
        color: #435b71;
        display: inline-block;
        margin-bottom: 7px;
    }

    .brick__tagline {
        display: block;
        font-size: 16px;
        line-height: 22px;
        color: #435b71;
    }

    .brick__caption-upper {
        padding: 19px 20px 13px;
        min-height: 110px;
    }

    .brick__caption-lower {
        border-top: 1px solid rgba(67, 91, 113, .1);
        padding: 11px 20px 13px;
        display: flex;
        justify-content: space-between;
    }
</style>
