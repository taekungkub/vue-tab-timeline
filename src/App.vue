<template>
  <div class="container mt-20">
    <div class="text-3xl font-bold mb-5">Tabs</div>

    <TabsList :number="6">
      <TabsItem label="Title" :hide-left="true" :active="selectedTab === enumTabs.one" @toggle="selectedTab = enumTabs.one">1</TabsItem>
      <TabsItem label="MyTabs" :active="selectedTab === enumTabs.two" @toggle="selectedTab = enumTabs.two">2</TabsItem>
      <TabsItem label="MyTabs" :active="selectedTab === enumTabs.three" @toggle="selectedTab = enumTabs.three">3</TabsItem>
      <TabsItem label="MyTabs" :active="selectedTab === enumTabs.four" @toggle="selectedTab = enumTabs.four">4</TabsItem>
      <TabsItem label="MyTabs" :active="selectedTab === enumTabs.five" @toggle="selectedTab = enumTabs.five">5</TabsItem>
      <TabsItem label="Title" :hide-right="true" :active="selectedTab === enumTabs.six" @toggle="selectedTab = enumTabs.six">6</TabsItem>
    </TabsList>

    <div class="content">
      <div class="content-inner">
        current tabs
        {{ selectedTab }}
      </div>
    </div>

    <div class="my-24">
      <div class="text-3xl font-bold mb-10">Timeline</div>

      <TabsList vertical>
        <TimelineItemVertical label="1" header="Collect and clean data">
          Jesse fetches fresh data from different exchanges, fills missing data, and stores them in the database. You can then use it in Jesse or even Jupyter
          notebooks.
        </TimelineItemVertical>
        <TimelineItemVertical label="2" header="Collect and clean data">
          is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an
          unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into
          electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum
          passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
        </TimelineItemVertical>

        <TimelineItemVertical label="3" header="Collect and clean data" :hide-line="true">
          It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem
          Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable
          English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will
          uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected
          humour and the like).
        </TimelineItemVertical>
      </TabsList>
    </div>

    <BaseModal v-model="openModal" title="Title" titleCenter="center"> </BaseModal>

    <div class="flex justify-end">
      <BaseDropdown v-model="openDropdown" placement="left">
        <BaseDropdownItem to="/asdadadsad">Profile</BaseDropdownItem>
        <BaseDropdownItem>Settings</BaseDropdownItem>
        <BaseDropdownItem>Help</BaseDropdownItem>
        <BaseDropdownItem>Orders</BaseDropdownItem>
        <BaseDropdownItem>Support</BaseDropdownItem>
      </BaseDropdown>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import TabsItem from "./components/TabsItem.vue";
import TabsList from "./components/TabsList.vue";
import TimelineItemVertical from "./components/TimelineItemVertical.vue";
import BaseModal from "./components/BaseModal.vue";
import BaseDropdown from "./components/BaseDropdown.vue";
import BaseDropdownItem from "./components/BaseDropdownItem.vue";

const enumTabs = {
  one: 1,
  two: 2,
  three: 3,
  four: 4,
  five: 5,
  six: 6,
};

const selectedTab = ref(1);

const openModal = ref(false);
const openDropdown = ref(false);
</script>

<style scoped lang="scss">
.container {
  @apply max-w-[1280px] mx-auto;
}

.content {
  @apply p-3 rounded-xl bg-slate-800 border text-white;
}

.content-inner {
  @apply p-5 rounded-lg bg-slate-700 border text-white;
}
</style>
