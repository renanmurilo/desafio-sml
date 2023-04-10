<script>
import LogoIcon from './icons/IconLogo.vue';
import SearchIcon from './icons/IconSearch.vue';
import CircleIcon from './icons/IconCircle.vue';
import LanguageIcon from './icons/IconLanguage.vue';
import NotifyIcon from './icons/IconNotify.vue';
import ArrowIcon from './icons/IconArrow.vue';
import MenuIcon from './icons/IconMenu.vue';
import Dark from './icons/IconColor.vue';

export default {
    components: {
        LogoIcon,
        SearchIcon,
        CircleIcon,
        LanguageIcon,
        NotifyIcon,
        ArrowIcon,
        MenuIcon,
        Dark,
    },
    data() {
        return {
            showMenu: false,
        };
    },
    methods: {
        color(param) {
            let color = localStorage.color;

            if (color) {
                window.localStorage.removeItem('color');
            } else {
                window.localStorage.color = param;
            }
            location.reload();
        },
    },
};
</script>

<template>
    <header>
        <div class="shell">
            <div class="content__header">
                <a @click.stop.prevent="showMenu = true" class="open__menu">
                    <MenuIcon />
                </a>
                <div class="widget">
                    <a href="/">
                        <LogoIcon />
                    </a>

                    <a href="" class="descativated"> Desativar Impersonar </a>
                </div>

                <div class="widget">
                    <a class="search">
                        <SearchIcon />
                    </a>

                    <a class="circle">
                        <CircleIcon />
                    </a>
                    <a class="notifi">
                        <NotifyIcon />
                    </a>
                    <a class="language">
                        <LanguageIcon />

                        <a class="arrow">
                            <ArrowIcon />
                        </a>
                    </a>
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

                    <a class="icon__color" @click.stop.prevent="color">
                        <Dark />
                    </a>
                </div>
            </div>

            <nav :class="{ active: showMenu }">
                <a @click.stop.prevent="showMenu = false" class="close"> x </a>

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

    @media ($mobile) {
        height: 12rem;
    }

    .content__header {
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        flex-wrap: wrap;
        padding: 1.625rem 0;
        height: 100%;

        .open__menu {
            display: none;

            @media ($mobile) {
                display: block;
                position: absolute;
                top: 0.5rem;
                left: 1rem;
                width: 1.5625rem;
                height: 1.5625rem;
            }
        }

        .widget {
            display: flex;
            align-items: center;
            width: 40%;

            @media ($mobile) {
                width: 100%;
                justify-content: space-between;
                padding-top: 1.5rem;
            }

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

            .icon__color {
                position: absolute;
                top: 2rem;
                right: 2rem;
                filter: invert(1);

                @media ($mobile) {
                    top: 1rem;
                }
            }
        }
    }

    nav {
        display: flex;
        width: 100%;
        padding-bottom: 0.5rem;
        margin-left: 3.2rem;

        @media ($mobile) {
            position: fixed;
            top: 0;
            left: 0;
            height: 100vh;
            background-color: $primary;
            width: 14.75rem;
            margin-left: 0;
            z-index: 1;
            padding-top: 2rem;
            padding-left: 2rem;
            transform: translateX(-1000px);
            transition: all 0.4s;

            &.active {
                transform: translateX(0);
                transition: all 0.4s;
            }
        }

        .close {
            display: none;

            @media ($mobile) {
                display: block;
                position: absolute;
                top: 2rem;
                right: 1.5rem;
                color: $white;
                @include font-inter(1rem, 400);
            }
        }

        .nav__bar {
            display: flex;
            width: 100%;

            @media ($mobile) {
                flex-direction: column;
            }

            .nav__link {
                margin-right: 5.625rem;

                @media ($mobile) {
                    margin-right: 0;
                    margin-bottom: 2rem;
                }

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