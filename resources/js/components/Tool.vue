<template>
    <div>
        <h4 ref="nova-category" class="ml-6 leading-wide font-bold text-white-80% mb-4 text-md capitalize cursor-pointer hover:text-white" @click.prevent="toggle">
            <span v-html="header"></span>
            <template v-if="expanded">&minus;</template>
            <template v-else>&plus;</template>
        </h4>

        <transition-group tag="ul" class="list-reset" :class="{'mb-6': last }">
            <slot v-if="expanded"></slot>
        </transition-group>
    </div>
</template>

<script>
    export default {
        props: {
            header: String,
            last: Boolean,
        },
        data() {
            return {
                expanded: true,
            };
        },
        methods: {
            toggle() {
                this.expanded = !this.expanded
            }
        }
    }
</script>
