<template>

  <div>

    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" v-for="tab in tabs" :class="{active: tab.active}">
        <a :href="tab.href" @click="select(tab)" aria-controls="team" role="tab">
          {{ tab.name }}
        </a>
      </li>
    </ul>
    <div class="tab-content">
      <slot></slot>
    </div>

  </div>
</template>

<script>

    export default {
        data(){
            return {
                tabs: [],
            }
        },
        methods: {
            select(tab){
                this.tabs.forEach(x => x.active = (tab === x));
            },
            selectFromHash(){
                let active = this.tabs.find(x => x.href === window.location.hash);
                if (active){
                    this.select(active);
                }
            }
        },
        mounted() {
            this.tabs = this.$children;

            window.addEventListener('hashchange', this.selectFromHash, false);

            this.selectFromHash();

        },
        destroyed() {

            window.removeEventListener('hashchange', this.selectFromHash);
        }
    }
</script>
