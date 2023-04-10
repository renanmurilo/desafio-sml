<script setup>
import EditIcon from '@/components/icons/IconEdit.vue';
import CheckIcon from '@/components/icons/IconCheck.vue';
import TreinoIcon from '@/components/icons/IconTreino.vue';
import MetasIcon from '@/components/icons/IconMetas.vue';
import IconRight from '@/components/icons/IconArrowRight.vue';
import Dots from '@/components/icons/IconDots.vue';
</script>

<template>
    <div class="pendencias">
        <div class="header__pendencias">
            <h3>Pendências <span>2</span></h3>

            <a href="" class="btn__more"><Dots /></a>
        </div>

        <div class="content__pendencias">
            <div class="grid">
                <div class="icon">
                    <EditIcon />
                </div>

                <div class="description">
                    <h4>Assinaturas Digitais <span>2 mins ago</span></h4>
                    <p>
                        Você tem <span>52 assinaturas digitais</span> para
                        validar
                    </p>

                    <a href="" class="link">
                        Resolver agora <span><IconRight /></span>
                    </a>
                </div>
            </div>

            <div class="grid">
                <div class="icon">
                    <CheckIcon />
                </div>

                <div class="description">
                    <h4>Avaliações <span>2 mins ago</span></h4>
                    <p>Você tem <span>02 Avaliações</span> para conferir</p>

                    <a href="" class="link">
                        Resolver agora <span><IconRight /></span>
                    </a>
                </div>
            </div>

            <div class="grid">
                <div class="icon">
                    <TreinoIcon />
                </div>

                <div class="description">
                    <h4>Treinamento <span>2 mins ago</span></h4>
                    <p>Você tem <span>18 treinamento</span> esperando você</p>

                    <a href="" class="link">
                        Resolver agora <span><IconRight /></span>
                    </a>
                </div>
            </div>

            <div class="grid">
                <div class="icon">
                    <MetasIcon />
                </div>

                <div class="description">
                    <h4>Metas <span>2 mins ago</span></h4>
                    <p>Você tem <span>06 Metas</span> esperando você</p>

                    <a href="" class="link">
                        Resolver agora <span><IconRight /></span>
                    </a>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
.pendencias {
    width: 100%;
    min-height: 32.6875rem;
    background-color: $white;
    box-shadow: 0px 0.0625rem 0.1875rem rgba(16, 24, 40, 0.1),
        0px 0.0625rem 0.125rem rgba(16, 24, 40, 0.06);
    border-radius: 0.75rem;
    padding: 1.375rem 1.3125rem;

    .header__pendencias {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
        padding-bottom: 0.8125rem;
        border-bottom: 0.0625rem solid $border;

        h3 {
            @include font-inter(1rem, 600, 0);
            color: $text-light;
            display: flex;
            align-items: center;

            span {
                background-color: #ff5630;
                border-radius: 100%;
                height: 1.1875rem;
                width: 1.1875rem;
                display: flex;
                justify-content: center;
                align-items: center;
                @include font-inter(0.75rem, 500);
                color: $white;
                position: relative;
                left: 1rem;
            }
        }
    }

    .content__pendencias {
        width: 100%;
        margin-top: 1rem;

        .grid {
            width: 100%;
            margin-bottom: 1.75rem;
            display: flex;

            &:last-child {
                .icon {
                    &::before {
                        display: none;
                    }
                }
            }

            .icon {
                width: 3rem;
                margin-right: 0.75rem;
                position: relative;

                &::before {
                    content: '';
                    width: 0.125rem;
                    height: 3rem;
                    background: $barra;
                    position: absolute;
                    bottom: -1.5rem;
                    left: 0;
                    right: 0;
                    margin: auto;
                }
            }

            .description {
                margin-top: 0.3rem;
                h4 {
                    @include font-inter(0.875rem, 500, 0);
                    color: $text;

                    span {
                        font-size: 0.75rem;
                        font-weight: 400;
                    }
                }
                p {
                    @include font-inter(0.875rem, 500, 0);
                    color: $text-light;
                    margin: 0.5rem 0 0.75rem;

                    span {
                        font-weight: 400;
                        color: $lilas-light;
                    }
                }

                .link {
                    @include font-inter(0.875rem, 600, 0);
                    color: $blue;
                    transition: all 0.4s;
                    display: flex;

                    span {
                        margin-left: 0.4rem;
                    }

                    @media ($tabletMin) {
                        &:hover {
                            color: $lilas-dark;
                            transition: all 0.4s;
                        }
                    }
                }
            }
        }
    }
}
</style>