<script setup>
</script>

<template>
    <div class="menu__dashboad">
        <ul class="menu__list">
            <li class="menu__item">
                <a href="" class="menu__link active">Início</a>
            </li>
            <li class="menu__item">
                <a href="" class="menu__link">Meu Dashboard</a>
            </li>
            <li class="menu__item"><a href="" class="menu__link">Chat</a></li>
            <li class="menu__item"><a href="" class="menu__link">Files</a></li>
        </ul>
    </div>
</template>

<style lang="scss">
.menu__dashboad {
    width: 100%;
    height: 3.25rem;
    background-color: $white;
    box-shadow: 0px 0.0625rem 0.1875rem rgba(16, 24, 40, 0.1),
        0rem 0.0625rem 0.125rem rgba(16, 24, 40, 0.06);
    border-radius: 0.75rem;
    margin-bottom: 1rem;

    .menu__list {
        display: flex;
        width: 100%;
        align-items: center;
        height: 100%;
        padding: 0 1.25rem;

        .menu__item {
            margin-right: 2rem;

            &:last-child {
                margin-right: 0;
            }

            .menu__link {
                @include font-inter(0.875rem, 600, 0);
                line-height: 1.25rem;
                color: $text-light;

                &.active {
                    color: $text;
                }
            }
        }
    }
}
</style>