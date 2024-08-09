<template>
    <div class="dropdown" :class="{ 'open': show }">
        <div @click="toggle">
            <slot name="toggle"></slot>
        </div>
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
        }
    }
}
</script>