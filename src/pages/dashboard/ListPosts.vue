<script>
import Like from '@/components/icons/IconLike.vue';
import Comment from '@/components/icons/IconComents.vue';
import Share from '@/components/icons/IconShare.vue';
import Dots from '@/components/icons/IconDots.vue';

export default {
    components: { Like, Comment, Share, Dots },
    data() {
        return {
            comment:
                'É TEXTÃO E É DE ❤️: A maioria que esta aqui comigo me conhece por causa do meu trabalho Talvez vocês nãosaibam, mas nos momentos mais complicados da minhacarreira, vocês estavam aqui me mandandotanta energiapositiva que me ajudaram a não desistir! E é por issoque sempre que eu posso faço questão de agradecer aparceria de vocês! 🙏🏼E hoje, nesse primeiro de maio, euagradeço pelo meu trabalho e por vocês me ajudarem arealiza-lo sempre com um sorriso no rosto. Queria MUITOque todos os trabalhadores desse Brasilzão fossemmerecem! Parece umarealidade distante, né? Mas não custa sonhar! Parabénspara você que luta diariamente para trabalhar e levar oustento da sua família mesmo diante de todas asdificuldades! E para você que não esta trabalhando:coragem e persistência!!! Dias melhores virão... se Deusquiser! ✨',
        };
    },
};
</script>

<template>
    <div class="list__posts">
        <div class="header__posts">
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

        <div class="inner__posts">
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

                <div class="message__post">
                    <p>
                        É TEXTÃO E É DE ❤️: A maioria que esta aqui comigo me
                        conhece por causa do meu trabalho Talvez vocês não
                        saibam, mas nos momentos mais complicados da minha
                        carreira, vocês estavam aqui me mandandotanta energia
                        positiva que me ajudaram a não desistir! E é por isso
                        que sempre que eu posso faço questão de agradecer a
                        parceria de vocês! 🙏🏼E hoje, nesse primeiro de maio, eu
                        agradeço pelo meu trabalho e por vocês me ajudarem a
                        realiza-lo sempre com um sorriso no rosto. Queria MUITO
                        que todos os trabalhadores desse Brasilzão fossem
                        respeitados e valorizados como merecem! Parece uma
                        realidade distante, né? Mas não custa sonhar! Parabéns
                        para você que luta diariamente para trabalhar e levar o
                        sustento da sua família mesmo diante de todas as
                        dificuldades! E para você que não esta trabalhando:
                        coragem e persistência!!! Dias melhores virão... se Deus
                        quiser! ✨

                        <a href="" class="link">Ler mais</a>
                    </p>

                    <div class="info__message">
                        <div class="widget">
                            <a href="" class="like">
                                <Like /> <span>103 Likes</span>
                            </a>
                        </div>

                        <div class="widget">
                            <a href="" class="comments">
                                <Comment /> <span>67 Comments</span>
                            </a>
                        </div>

                        <div class="widget">
                            <a href="" class="share">
                                <Share /> <span>105 Share</span>
                            </a>
                        </div>
                    </div>
                </div>

                <div class="comments__post">
                    <div class="box__comments">
                        <div class="image">
                            <img src="@/assets/bruno.png" alt="Bruno" />
                        </div>

                        <div class="comment">
                            <textarea
                                name=""
                                id=""
                                v-model="comment"
                                class="field"
                            ></textarea>

                            <p class="limit">
                                Você ultrapassou o limite de 1300 caracteres.
                            </p>
                        </div>
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

    .header__posts {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 1rem;

        h2 {
            @include font-inter(1rem, 500, 0);
            color: $text-light;
        }

        .order {
            display: flex;

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
            }
        }
    }

    .inner__posts {
        background-color: $white;
        box-shadow: 0px 0.0625rem 0.1875rem rgba(16, 24, 40, 0.1),
            0px 0.0625rem 0.125rem rgba(16, 24, 40, 0.06);
        border-radius: 0.75rem;
        width: 100%;
        padding: 1.0625rem 1.25rem;

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
            margin-top: 2.1875rem;

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

                    .field {
                        width: 100%;
                        border: 1px solid #bac7db;
                        border-radius: 0.75rem;
                        height: 16.25rem;
                        padding: 0.75rem 1.5rem 0.75rem 0.75rem;
                        color: $text;
                        @include font-inter(1rem, 400, 0);

                        &::-webkit-scrollbar {
                            width: 0;
                        }
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