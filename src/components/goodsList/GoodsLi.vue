<template>
  <li class="list"><goods-link v-bind="goods"></goods-link></li>
</template>

<script>
import GoodsLink from "./GoodsLink";
export default {
  components: { GoodsLink },
  props: {
    goods: Object,
  },
};
</script>

<style>
.list {
  width: 234px;
  height: 360px;
  background-color: #fafafa;
  border-top: 1px solid #ffa500;
  margin-bottom: 20px;
  margin-left: 4px;
  margin-right: 6px;
  list-style-type: none;
  display: flex;
  flex-direction: column;
}
</style>
