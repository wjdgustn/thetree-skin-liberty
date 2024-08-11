<template>
    <div ref="dropdown" class="dropdown" :class="{ 'open': show }">
        <div @click="toggle"><slot name="toggle"></slot></div>
        <slot v-if="show"></slot>
    </div>
</template>

<script>
export default {
    data() {
        return {
            show: false,
        }
    },
    methods: {
        toggle() {
            this.show = !this.show;
        },
        hide() {
            this.show = false;
        }
    },
    mounted() {
        document.addEventListener('click', this.hide);
    },
    beforeUnmount() {
        document.removeEventListener('click', this.hide);
    }
}
</script>