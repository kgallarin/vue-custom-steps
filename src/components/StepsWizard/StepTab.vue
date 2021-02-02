<template>
    <div
      class="tab-pane"
      role="tabpanel"
      :id="tabId"
      :aria-hidden="!active"
      :aria-labelledby="`step-${tabId}`"
      :class="{ 'active show': active }"
      v-show="active"
    >
      <!-- tab header -->
      <div :class="[{'steps--header d-flex': true}]">

        <p class="title">
          <strong>{{ title }}</strong>
        </p>

        <p v-if="tabCount > 0 && hasCounter" class="steps-header-counter"> {{ studio ? activeTab + 2 : activeTab + 1 }} / {{ studio ? tabCount + 1 : tabCount }}</p>
        
      </div>
      <slot></slot>
    </div>
</template>
<script>
export default {
  name: "StepsTab",
  props: {
    title: {
      type: String,
      default: ''
    },
    studio: {
      type: Boolean,
      default: false
    },
    hasLeftClose: {
        type: Boolean,
        default: false
    },
    beforeChange: Function
  },
  inject: ["addTab", "removeTab"],
  data() {
    return {
      active: false,
      checked: false,
      hasError: false,
      tabId: ""
    };
  },
  mounted() {
    this.addTab(this);
  },
  destroyed() {
    if (this.$el && this.$el.parentNode) {
      this.$el.parentNode.removeChild(this.$el);
    }
    this.removeTab(this);
  },
  computed: {}
};
</script>

<style>
.tab-pane {
  -webkit-animation-duration: .5s;
  animation-duration: .5s;
  -webkit-animation-duration: .5s;
  animation-duration: .5s;
  -webkit-animation-fill-mode: both;
  animation-fill-mode: both;
  
  -webkit-animation-delay: .3s;
  animation-delay: .3s;
  -webkit-animation-delay: .3s;
  animation-delay: .3s;
  
  -webkit-animation-name: fadeIn;
  animation-name: fadeIn;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  66% {
    opacity: 1;
  }
  to {
    opacity: 1;
  }
}
</style>
