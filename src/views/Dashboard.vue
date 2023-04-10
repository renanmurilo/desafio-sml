<script>
import Index from '@/pages/dashboard/Index.vue';
export default {
    components: {
        Index,
    },
    created() {
        let color = localStorage.color;

        if (color) {
            this.active = true;
        }
    },
    data() {
        return {
            active: false,
        };
    },
};
</script>

<template>
    <div class="body__dashboard" :class="{ color: active }">
        <Index />
    </div>
</template>

<style lang="scss">
.body__dashboard {
    width: 100%;
    padding-top: 2rem;

    &.color {
        background-color: #1e1e1e;

        .menu__dashboad .menu__list,
        .create .form__create,
        .create .form__create .form__row .field,
        .enquetes,
        .pendencias,
        .list__posts .inner__posts {
            background-color: #1d2939;
        }

        .list__posts .header__posts .order .select__field {
            background-color: #1e1e1e;
        }

        .enquetes .content__enquetes .form__field .form__row .barra,
        .enquetes
            .content__enquetes
            .form__field
            .form__row
            .label__field:before {
            background-color: #475467;
            border-color: #475467;
        }

        .enquetes
            .content__enquetes
            .form__field
            .form__row
            .field:checked
            + label::after {
            background-color: #475467;
        }

        .menu__dashboad .menu__list .menu__item .menu__link.active,
        .enquetes .content__enquetes h2,
        .enquetes .header__enquetes h3,
        .pendencias .header__pendencias h3 {
            color: $white;
        }
    }
}
</style>