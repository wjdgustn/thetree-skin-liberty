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
        hide(e) {
            if (this.show) {
                if (!this.$refs.dropdown.contains(e.target) || this.$slots.default[1].elm.contains(e.target)) this.show = false;
            }
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