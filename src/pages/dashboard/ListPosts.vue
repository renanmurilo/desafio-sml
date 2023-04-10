<script>
import Like from '@/components/icons/IconLike.vue';
import Comment from '@/components/icons/IconComents.vue';
import Share from '@/components/icons/IconShare.vue';
import Dots from '@/components/icons/IconDots.vue';
import limitLetter from '@/utils/limitLetter';
import Send from '@/components/icons/IconSend.vue';

export default {
    components: { Like, Comment, Share, Dots, Send },
    mixins: [limitLetter],
    created() {
        let posts = localStorage.posts;
        let comments = localStorage.comments;

        if (posts) {
            this.posts = JSON.parse(posts);
        }

        if (comments) {
            this.comments = JSON.parse(comments);
        }
    },
    data() {
        return {
            comment: '',
            facebook: `https://www.facebook.com/sharer.php?u=${window.location.href}`,
            posts: [],
            more: 798,
            comments: [],
            showComment: false,
            like: 0,
        };
    },
    methods: {
        sendComment() {
            this.comments.push({ comment: this.comment });
            localStorage.comments = JSON.stringify(this.comments);
            this.comment = '';
            this.showComment = false;
        },
    },
};
</script>

<template>
    <div class="list__posts">
        <div class="header__posts" v-if="posts.length">
            <h2>Ordenar suas postagens</h2>

            <div class="order">
                <select name="" id="" class="select__field">
                    <option value="">Recentes</option>
                </select>

                <select name="" id="" class="select__field">
                    <option value="">Filtrar por</option>
                </select>
            </div>
        </div>

        <div class="inner__posts" v-if="posts.length">
            <div class="post">
                <div class="dados__post">
                    <div class="image">
                        <img src="@/assets/bruno.png" alt="Bruno" />
                    </div>

                    <div class="dados">
                        <h3 class="name">Bruno Delorence</h3>
                        <p class="time">27 mins ago</p>
                    </div>

                    <a href="" class="btn__more"><Dots /></a>
                </div>

                <div
                    class="message__post"
                    v-for="(post, index) in posts"
                    :key="index"
                >
                    <p>
                        {{ this.limitLetter(post.mensagem, this.more) }}

                        <a
                            @click.stop.prevent="more = 2000"
                            class="link"
                            v-if="more <= 798 || more >= 500"
                        >
                            Ler mais
                        </a>
                    </p>

                    <div class="info__message">
                        <div class="widget">
                            <a
                                @click.stop.prevent="like = +1"
                                class="like"
                                :class="{ active: like > 0 }"
                            >
                                <Like /> <span>{{ like }} Likes</span>
                            </a>
                        </div>

                        <div class="widget">
                            <a
                                @click.stop.prevent="showComment = true"
                                class="comments"
                            >
                                <Comment />
                                <span
                                    >{{
                                        comments.length > 0
                                            ? comments.length
                                            : 0
                                    }}
                                    Comments
                                </span>
                            </a>
                        </div>

                        <div class="widget">
                            <a :href="facebook" class="share">
                                <Share /> <span>105 Share</span>
                            </a>
                        </div>
                    </div>
                </div>

                <div class="comments__post" :class="{ active: showComment }">
                    <div class="box__comments">
                        <div class="image">
                            <img src="@/assets/bruno.png" alt="Bruno" />
                        </div>

                        <form
                            class="comment"
                            @submit.stop.prevent="sendComment"
                        >
                            <textarea
                                name=""
                                id=""
                                v-model="comment"
                                class="field"
                                :class="{ active: showComment }"
                            ></textarea>

                            <p class="limit" v-if="comment.length > 1300">
                                Você ultrapassou o limite de 1300 caracteres.
                            </p>

                            <button type="submit" class="send">
                                <Send />
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
.list__posts {
    width: 100%;
    margin-top: 1rem;

    @media ($mobile) {
        margin-top: 2rem;
    }

    .header__posts {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 1rem;
        flex-wrap: wrap;

        h2 {
            @include font-inter(1rem, 500, 0);
            color: $text-light;
        }

        .order {
            display: flex;

            @media ($mobile) {
                justify-content: space-between;
                margin-top: 2rem;
            }

            .select__field {
                color: $text;
                @include font-inter(1rem, 400, 0);
                border: none;
                width: 5.4375rem;
                margin-left: 1.5rem;
                background-image: url(@/assets/arrow-down.svg);
                background-repeat: no-repeat;
                background-size: 10px;
                background-position: 100% 60%;
                appearance: none;
                -moz-appearance: none;
                -webkit-appearance: none;

                @media ($mobile) {
                    margin-left: 0;
                    margin-right: 1.5rem;
                }
            }
        }
    }

    .inner__posts {
        background-color: $white;
        box-shadow: 0px 0.0625rem 0.1875rem rgba(16, 24, 40, 0.1),
            0px 0.0625rem 0.125rem rgba(16, 24, 40, 0.06);
        border-radius: 0.75rem;
        width: 100%;
        padding: 2.0625rem 1.25rem;

        .dados__post {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
            position: relative;
            width: 100%;

            .image {
                widows: 2.5rem;
                margin-right: 0.8125rem;
            }

            .dados {
                display: flex;
                flex-direction: column;
                .name {
                    @include font-inter(0.875rem, 600, 0);
                    color: #4e5d78;
                }

                .time {
                    @include font-inter(0.75rem, 500, 0);
                    color: #b0b7c3;
                }
            }

            .btn__more {
                position: absolute;
                right: 0;
                top: 0;
                bottom: 0;
                margin: auto;
            }
        }

        .message__post {
            width: 100%;

            p {
                @include font-inter(0.875rem, 500, 0);
                color: #434e6c;
                line-height: 1.75rem;
            }

            .link {
                color: $blue;
            }

            .info__message {
                display: flex;
                align-items: center;
                width: 100%;
                margin-top: 1.4375rem;

                .widget {
                    margin-right: 3.125rem;
                    display: flex;
                    align-items: center;

                    a {
                        display: flex;
                        align-items: center;
                        @include font-inter(0.75rem, 500, 0);

                        span {
                            margin-left: 0.4rem;
                        }
                    }

                    .like {
                        color: $blue;
                        filter: grayscale(1);

                        &.active {
                            filter: grayscale(0);
                        }
                    }

                    .comments,
                    .share {
                        color: #b0b7c3;
                    }
                }
            }
        }

        .comments__post {
            width: 100%;
            visibility: hidden;
            height: 0%;
            opacity: 0;

            &.active {
                height: 100%;
                margin-top: 2.1875rem;
                visibility: visible;
                opacity: 1;
            }

            .box__comments {
                display: flex;
                width: 100%;

                .image {
                    width: 2.1875rem;
                    margin-right: 0.6875rem;
                }

                .comment {
                    width: 93%;
                    height: 100%;
                    position: relative;

                    .field {
                        width: 100%;
                        border: 1px solid #bac7db;
                        border-radius: 0.75rem;
                        height: 0%;
                        color: $text;
                        @include font-inter(1rem, 400, 0);

                        &::-webkit-scrollbar {
                            width: 0;
                        }

                        &.active {
                            padding: 0.75rem 1.5rem 0.75rem 0.75rem;
                            height: 16.25rem;
                        }
                    }

                    .send {
                        position: absolute;
                        bottom: -2rem;
                        right: 0;
                        background: transparent;
                        border: none;
                    }

                    .limit {
                        color: #f55065;
                        @include font-inter(0.75rem, 500, 0);
                        margin-top: 0.5rem;
                    }
                }
            }
        }
    }
}
</style>