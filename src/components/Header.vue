<script setup>
import LogoIcon from './icons/IconLogo.vue';
import SearchIcon from './icons/IconSearch.vue';
import CircleIcon from './icons/IconCircle.vue';
import LanguageIcon from './icons/IconLanguage.vue';
import NotifyIcon from './icons/IconNotify.vue';
import ArrowIcon from './icons/IconArrow.vue';
</script>

<template>
    <header>
        <div class="shell">
            <div class="content__header">
                <div class="widget">
                    <a href="/">
                        <LogoIcon />
                    </a>

                    <a href="" class="descativated"> Desativar Impersonar </a>
                </div>

                <div class="widget">
                    <div class="search">
                        <SearchIcon />
                    </div>

                    <div class="circle">
                        <CircleIcon />
                    </div>
                    <div class="notifi">
                        <NotifyIcon />
                    </div>
                    <div class="language">
                        <LanguageIcon />

                        <div class="arrow">
                            <ArrowIcon />
                        </div>
                    </div>
                    <div class="profile">
                        <div class="description">
                            <div class="image">
                                <img
                                    src="@/assets/red.png"
                                    alt="Imagem profile"
                                />
                            </div>

                            <div class="text">
                                <h3 class="name">Amanda Oliveira</h3>
                                <h4 class="cargo">Diretora</h4>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <nav>
                <ul class="nav__bar">
                    <li class="nav__link">
                        <a href="/">Início</a>
                    </li>
                    <li class="nav__link">
                        <a href="">Equipe</a>
                    </li>
                    <li class="nav__link">
                        <a href="">Metas</a>
                    </li>
                    <li class="nav__link">
                        <a href="">OKR</a>
                    </li>
                    <li class="nav__link">
                        <a href="">Desempenho</a>
                    </li>
                    <li class="nav__link">
                        <a href="">Sucessão</a>
                    </li>
                    <li class="nav__link">
                        <a href="">Treinamento</a>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
</template>

<style lang="scss">
header {
    background-color: $primary;
    width: 100%;
    height: 8.25rem;
    border-bottom: 0.25rem solid $rose;

    .content__header {
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1.625rem 0;
        height: 100%;

        .widget {
            display: flex;
            align-items: center;
            width: 36.5%;

            .descativated {
                width: 9.875rem;
                margin-left: 0.9387rem;
                color: $white;
                @include font-inter(0.875rem, 500, 0);
                background-color: $lilas;
                border-radius: 0.25rem;
                display: flex;
                align-items: center;
                justify-content: center;
                height: 1.875rem;
            }

            .circle {
                margin-left: 1.75rem;
            }

            .notifi {
                margin-left: 2.0737rem;
                position: relative;

                &::before {
                    content: '';
                    width: 0.7937rem;
                    height: 0.7937rem;
                    background-color: $rose;
                    border: 0.1587rem solid $primary;
                    position: absolute;
                    border-radius: 100%;
                    top: -0.125rem;
                    right: -0.1875rem;
                }
            }

            .language {
                margin-left: 2.1356rem;
                display: flex;
                align-items: center;

                .arrow {
                    margin-left: 0.4863rem;
                }
            }

            .profile {
                margin-left: 0.8975rem;

                .description {
                    display: flex;

                    .image {
                        width: 2.5rem;
                        margin-right: 0.75rem;

                        img {
                            object-fit: cover;
                        }
                    }

                    .text {
                        display: flex;
                        flex-direction: column;
                        justify-content: center;

                        .name {
                            @include font-inter(0.875rem, 600, 0);
                            color: $white;
                            line-height: 1.0588rem;
                        }

                        .cargo {
                            @include font-inter(0.9075rem, 300, 0);
                            color: $white;
                            line-height: 0.9075rem;
                            margin-top: 0.25rem;
                        }
                    }
                }
            }
        }
    }

    nav {
        display: flex;
        width: 100%;
        padding-bottom: 0.5rem;
        margin-left: 3.2rem;

        .nav__bar {
            display: flex;
            width: 100%;

            .nav__link {
                margin-right: 5.625rem;

                &:last-child {
                    margin-right: 0;
                }

                &:nth-child(1) {
                    a {
                        opacity: 1;
                    }
                }

                a {
                    @include font-inter(1rem, 600, 0);
                    color: $white;
                    opacity: 0.6;
                }
            }
        }
    }
}
</style>