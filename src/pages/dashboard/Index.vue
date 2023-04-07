<script setup>
import MenuDashboard from './MenuDashboard.vue';
import Enquetes from './Enquetes.vue';
import Pendencias from './Pendencias.vue';
</script>

<template>
    <div class="shell__dashboard">
        <div class="content__dashboard">
            <MenuDashboard />

            <div class="inner__dashboard">
                <div class="content__posts__dashboard"></div>
                <aside class="aside__dashboard">
                    <Enquetes />

                    <Pendencias />
                </aside>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
.content__dashboard {
    width: 100%;

    .inner__dashboard {
        width: 100%;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;

        .content__posts__dashboard {
            width: 100%;
            max-width: 47rem;
        }

        .aside__dashboard {
            width: 100%;
            max-width: 28.5rem;
        }
    }
}
</style>