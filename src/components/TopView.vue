<template>
  <div class="card">
    <header class="card-header">
      <ul class="tab-heads">
        <li
          class="tab-head"
          v-for="tab in tabs"
          :key="tab"
          :class="{
            'tab-head--active': activeTab === tab
          }"
          v-on:click="switchTab(tab);"
        >
          <slot :name="tabHeadSlotName(tab)">
            {{  tab  }}
          </slot>
        </li>
      </ul>
    </header>
    <main class="card-body">
      <div class="tab-panel">
        <slot :name="tabPanelSlotName"></slot>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: 'top-view:',
  props: {
    initialTab: String,
    tabs: Array
  },
  data() {
    return {
      activeTab: this.initialTab
    };
  },
  computed: {
    tabPanelSlotName() {
      return `tab-panel-${this.activeTab}`;
    }
  },
  methods: {
    tabHeadSlotName(tabName) {
      return `tab-head-${tabName}`;
    },

    switchTab(tabName) {
      this.activeTab = tabName;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card-header ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: black;
}

.card-header li {
  float: left;
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

/* Change the link color to #111 (black) on hover */
.card-header li:hover {
  background-color: red;
}
.card-header .tab-head--active{
  background-color: green;
}

.card-body ul {
  text-align: left;
}
.card-body li {
  
}
.card-body p {
  text-align: left;
}
</style>
