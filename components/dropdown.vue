<template>
    <div class="dropdown">
        <a class="nav-link dropdown-toggle dropdown-toggle-fix" href="#" data-toggle="dropdown" aria-expanded="false" @click.prevent>
            <span class="fa fa-gear"></span><span class="hide-title">도구</span>
        </a>
        <div class="dropdown-menu">
            <slot></slot>
        </div>
    </div>
</template>

<sytle module>
.dropdown-menu {
    font-size: 0.95rem;
    box-shadow: 0 6px 12px rgba(0,0,0,.175);
    border-color: #e1e8ed;
}

.dropdown-menu .dropdown-item:hover {
    background-color: var(--liberty-brand-color, #4188f1);
    color: #fff;
    transition: 0.3s;
}

.dropdown-divider {
    border-color: #e1e8ed;
}
</sytle>

<script>
export default {
    props: {

    },
    data () {
        return {

        };
    },
    methods: {

    }
}
</script>