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

        <!-- <a href="#" v-if="hasLeftClose" class="header-left-close" @click="() => { this.$EventBus.$emit('closePop') }">
          (*__*)
        </a> -->

        <p class="title">
          <strong>{{ title }}</strong>
        </p>

        <!-- <a href="#" v-if="hasClose" @click="() => { this.$EventBus.$emit('closePop') }">
          (*___*)
        </a> -->

        <!-- <p v-if="tabCount > 0 && hasCounter" class="steps-header-counter"> {{ studio ? activeTab + 2 : activeTab + 1 }} / {{ studio ? tabCount + 1 : tabCount }}</p> -->
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
