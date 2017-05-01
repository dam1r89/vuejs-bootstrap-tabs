<template>
  <div role="tabpanel" class="tab-pane" :class="{active: active}">
    <slot></slot>
  </div>
</template>

<script>
    export default {
        props: ['name', 'selected'],
        data() {
            return {
                active: false
            }
        },
        computed: {
            href(){
                return '#' + this.name.toLowerCase().replace(/[^A-Za-z]+/g, '-');
            }
        },
        mounted() {
            this.active = this.selected !== undefined;
        }
    }
</script>
