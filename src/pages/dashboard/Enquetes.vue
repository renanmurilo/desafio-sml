<script>
import Dots from '@/components/icons/IconDots.vue';

export default {
    components: { Dots },
    data() {
        return {
            selected: 'todos',
        };
    },
};
</script>

<template>
    <div class="enquetes">
        <div class="header__enquetes">
            <h3>Enquetes</h3>

            <a href="" class="btn__more"><Dots /></a>
        </div>

        <div class="content__enquetes">
            <h2>Como perder peso em 2023</h2>

            <form action="" class="form__field">
                <div class="form__row">
                    <input
                        type="radio"
                        :name="`1hora`"
                        :value="`1hora`"
                        id="1hora"
                        class="field"
                        v-model="selected"
                    />

                    <label for="1hora" class="label__field">
                        1 hora de esteira
                    </label>

                    <p class="quantity">12 votos</p>
                    <div class="barra"><span></span></div>
                </div>

                <div class="form__row">
                    <input
                        type="radio"
                        :name="`1treino`"
                        :value="`1treino`"
                        id="1treino"
                        class="field"
                        v-model="selected"
                    />

                    <label for="1treino" class="label__field">
                        1 hora de treino de musculação
                    </label>

                    <p class="quantity">12 votos</p>
                    <div class="barra"><span></span></div>
                </div>

                <div class="form__row">
                    <input
                        type="radio"
                        :name="`alimentacao`"
                        :value="`alimentacao`"
                        id="alimentacao"
                        class="field"
                        v-model="selected"
                    />

                    <label for="alimentacao" class="label__field">
                        Alimentação equilibrada
                    </label>

                    <p class="quantity">12 votos</p>
                    <div class="barra"><span></span></div>
                </div>

                <div class="form__row">
                    <input
                        type="radio"
                        :name="`5litros`"
                        :value="`5litros`"
                        id="5litros"
                        class="field"
                        v-model="selected"
                    />

                    <label for="5litros" class="label__field">
                        5 litros de água por dia
                    </label>

                    <p class="quantity">12 votos</p>
                    <div class="barra"><span></span></div>
                </div>

                <div class="form__row">
                    <input
                        type="radio"
                        :name="`suplementacao`"
                        :value="`suplementacao`"
                        id="suplementacao"
                        class="field"
                        v-model="selected"
                    />

                    <label for="suplementacao" class="label__field">
                        Suplementação (Whey + Creatina)
                    </label>

                    <p class="quantity">12 votos</p>
                    <div class="barra"><span></span></div>
                </div>

                <div class="form__row">
                    <input
                        type="radio"
                        :name="`todos`"
                        :value="`todos`"
                        id="todos"
                        class="field"
                        v-model="selected"
                    />

                    <label for="todos" class="label__field">
                        Todas as opções estão corretas
                    </label>

                    <p class="quantity">12 votos</p>
                    <div class="barra"><span></span></div>
                </div>
            </form>
        </div>
    </div>
</template>

<style lang="scss">
.enquetes {
    width: 100%;
    min-height: 32.6875rem;
    background-color: $white;
    box-shadow: 0px 0.0625rem 0.1875rem rgba(16, 24, 40, 0.1),
        0px 0.0625rem 0.125rem rgba(16, 24, 40, 0.06);
    border-radius: 0.75rem;
    padding: 1.375rem 1.3125rem;
    margin-bottom: 1.1875rem;

    .header__enquetes {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
        padding-bottom: 0.8125rem;
        border-bottom: 0.0625rem solid $border;

        h3 {
            @include font-inter(1rem, 600, 0);
            color: $text-light;
        }
    }

    .content__enquetes {
        width: 100%;

        h2 {
            @include font-inter(0.875rem, 600, 0);
            color: $text-dark;
            margin: 1.5rem 0 1.125rem;
        }

        .form__field {
            width: 100%;

            .form__row {
                width: 100%;
                margin-bottom: 1.4375rem;
                position: relative;

                .label__field {
                    @include font-inter(0.75rem, 600, 0);
                    color: $text-light;
                    position: relative;
                    display: flex;
                    align-items: center;
                    cursor: pointer;

                    &:before {
                        content: '';
                        width: 1.25rem;
                        height: 1.25rem;
                        display: block;
                        background: $white;
                        border: 1px solid #d0d5dd;
                        border-radius: 0.625rem;
                        margin-right: 0.5rem;
                        transition: all 0.4s;
                    }

                    &::after {
                        content: '';
                        height: 12px;
                        width: 7px;
                        background: transparent;
                        border: 2px solid $border;
                        border-top: 0;
                        border-left: 0;
                        left: 6px;
                        top: 3px;
                        position: absolute;
                        transform: rotate(40deg);
                        opacity: 0;
                        transition: al 0.4s;
                    }

                    @media ($tabletMin) {
                        &:hover {
                            &::before {
                                border: 1px solid $lilas-dark;
                                background: $lilas opacity 0.8;
                                transition: all 0.4s;
                            }
                        }
                    }
                }

                .field {
                    display: none;

                    &:checked {
                        + label {
                            &:before {
                                background: $green;
                                border: 1px solid $green;
                                transition: al 0.4s;
                            }
                        }

                        + label {
                            &::after {
                                opacity: 1;
                                transition: all 0.4s;
                                background: $green;
                            }
                        }
                    }
                }

                .quantity {
                    position: absolute;
                    top: 0;
                    right: 0;
                    @include font-inter(0.75rem, 600, 0);
                    color: #b0b7c3;
                }

                .barra {
                    width: 24rem;
                    background-color: $background-light;
                    border-radius: 2.8125rem;
                    height: 0.5rem;
                    margin: 0.4375rem 0 0 auto;
                    position: relative;

                    &::before {
                        content: '';
                        width: 100%;
                        background-color: $green;
                        height: 0.5rem;
                        position: absolute;
                        left: 0;
                        border-radius: 2.8125rem;
                    }
                }

                &:nth-child(1) {
                    .barra {
                        &::before {
                            content: '';
                            width: 10rem;
                            background-color: $green;
                            height: 0.5rem;
                            position: absolute;
                            left: 0;
                            border-radius: 2.8125rem;
                        }
                    }
                }

                &:nth-child(2) {
                    .barra {
                        &::before {
                            content: '';
                            width: 20.9375rem;
                            background-color: $green;
                            height: 0.5rem;
                            position: absolute;
                            left: 0;
                            border-radius: 2.8125rem;
                        }
                    }
                }

                &:nth-child(3) {
                    .barra {
                        &::before {
                            content: '';
                            width: 3.1875rem;
                            background-color: $green;
                            height: 0.5rem;
                            position: absolute;
                            left: 0;
                            border-radius: 2.8125rem;
                        }
                    }
                }

                &:nth-child(4) {
                    .barra {
                        &::before {
                            content: '';
                            width: 17.25rem;
                            background-color: $green;
                            height: 0.5rem;
                            position: absolute;
                            left: 0;
                            border-radius: 2.8125rem;
                        }
                    }
                }

                &:nth-child(5) {
                    .barra {
                        &::before {
                            content: '';
                            width: 1.25rem;
                            background-color: $green;
                            height: 0.5rem;
                            position: absolute;
                            left: 0;
                            border-radius: 2.8125rem;
                        }
                    }
                }
            }
        }
    }
}
</style>