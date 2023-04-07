<script setup>
import MenuDashboard from './MenuDashboard.vue';
import Enquetes from './Enquetes.vue';
import Pendencias from './Pendencias.vue';
import CreatePosts from './CreatePosts.vue';
</script>

<template>
    <div class="shell__dashboard">
        <div class="content__dashboard">
            <MenuDashboard />

            <div class="inner__dashboard">
                <div class="content__posts__dashboard">
                    <CreatePosts />
                </div>

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
            max-width: 58.53%;
        }

        .aside__dashboard {
            width: 100%;
            max-width: 38%;
        }
    }
}
</style>