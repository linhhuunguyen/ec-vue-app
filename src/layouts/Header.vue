<template>
  <div>
    <p><fa icon="envelope" /> mhhasanul@gmail.com</p>
    <p><fa icon="phone" /> (12345) 67890</p>
    <a-select
      v-model:value="value"
      style="width: 120px"
      :options="items.map((item) => ({ value: item }))"
    >
      <template #dropdownRender="{ menuNode: menu }">
        <v-nodes :vnodes="menu" />
        <a-divider style="margin: 4px 0" />
        <div
          style="padding: 4px 8px; cursor: pointer"
          @mousedown="(e) => e.preventDefault()"
          @click="addItem"
        >
          <plus-outlined />
          Add item
        </div>
      </template>
    </a-select>
  </div>
</template>
<script lang="ts">
import { Vue } from "vue-class-component";
import { PlusOutlined } from "@ant-design/icons-vue";
import { defineComponent, ref } from "vue";

let index = 0;
export default defineComponent({
  components: {
    PlusOutlined,
    VNodes: (_, { attrs }) => {
      return attrs.vnodes;
    },
  },

  setup() {
    const items = ref(["jack", "lucy"]);
    const value = ref("lucy");

    const addItem = () => {
      console.log("addItem");
      items.value.push(`New item ${index++}`);
    };
    return {
      items,
      value,
      addItem,
    };
  },
});
</script>
<style lang="scss"></style>
