<template>
  <li>
    <a
      type="button"
      class="list-group-item list-group-item-action"
      :class="{ 'is-active': active }"
      :title="baseUrl"
      @click="handleClick"
    >
      {{ category.name }}
    </a>
  </li>
</template>

<script>
export default {
  props: ["category", "active"],
  data() {
    return {
      baseUrl: `https://t24.com.tr/rss/haber/${this.category.url}`,
    };
  },
  created() {
    // console.log(this.category, this.active);
  },
  methods: {
    handleClick() {
      this.$emit("changeCategory", this.category);
    },
  },
};
</script>

<style scoped>
.menu-list a.is-active {
  background-color: #00d1b2;
}
</style>
