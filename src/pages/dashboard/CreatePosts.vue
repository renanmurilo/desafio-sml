<script>
import IconVideo from '@/components/icons/IconVideo.vue';
import IconImage from '@/components/icons/IconImage.vue';
import Happy from '@/components/icons/IconHappy.vue';
export default {
    components: { IconVideo, IconImage, Happy },
};
</script>

<template>
    <div class="create">
        <form action="" class="form__create">
            <div class="form__row">
                <div class="image">
                    <img src="@/assets/image.png" alt="Image user" />
                </div>

                <textarea
                    placeholder="What's new with you?"
                    name=""
                    id=""
                    class="field"
                ></textarea>

                <div class="barra__items">
                    <div class="icons">
                        <input
                            type="file"
                            name="video"
                            id="video"
                            class="field"
                            accept="video/*"
                        />

                        <label for="video">
                            <IconVideo />
                        </label>
                    </div>

                    <div class="icons">
                        <input
                            type="file"
                            name="image"
                            id="image"
                            class="field"
                            accept="image/png, image/jpeg"
                        />
                        <label for="image">
                            <IconImage />
                        </label>
                    </div>

                    <div class="icons">
                        <input
                            type="file"
                            name="happy"
                            id="happy"
                            class="field"
                        />

                        <label for="happy">
                            <Happy />
                        </label>
                    </div>
                </div>
            </div>
        </form>
    </div>
</template>

<style lang="scss">
.create {
    width: 100%;
    background-color: $white;
    box-shadow: 0px 0.0625rem 0.1875rem rgba(16, 24, 40, 0.1),
        0px 0.0625rem 0.125rem rgba(16, 24, 40, 0.06);
    border-radius: 0.75rem;
    height: 8.1875rem;

    .form__create {
        width: 100%;
        padding: 1.25rem 1.5rem;
        height: 100%;

        .form__row {
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: flex-end;
            position: relative;

            .image {
                width: 2rem;
            }

            .field {
                width: 93%;
                margin: 0 0 0 auto;
                border-radius: 0.9375rem;
                height: 2.125rem;
                max-height: 3.5rem;
                display: flex;
                align-items: center;
                background-color: #fafbfc;
                color: #b0b7c3;
                @include font-inter(0.75rem, 500, 0);
                padding: 0.5rem 0.9375rem;
                border: 1px solid $barra;

                &::-webkit-scrollbar {
                    width: 0;
                }
            }

            .barra__items {
                position: absolute;
                bottom: 0;
                left: 0.7rem;
                display: flex;
                align-items: center;

                .icons {
                    margin-right: 2.4375rem;

                    .field {
                        display: none;
                    }
                }
            }
        }
    }
}
</style>
