<template>
  <div class="sidebar">
    <LeftNavBar />

    <div class="sidebar-content scrollbar">
      <div
        v-if="this.$store.state.selectedLeftNavTab === 'folders'"
        class="folders-content"
      >
        <NotebookList />
      </div>

      <div
        v-if="this.$store.state.selectedLeftNavTab === 'activity'"
        class="activity-content"
      >
        <ActivityConsole />
      </div>

      <div
        v-if="this.$store.state.selectedLeftNavTab === 'helium'"
        class="helium-content"
      >
        <PackageList />
      </div>

      <div
        v-if="this.$store.state.selectedLeftNavTab === 'trash'"
        class="trash-content"
      >

      </div>
    </div>
  </div>
</template>

<script>
import LeftNavBar from './LeftNavBar.vue'
import NotebookList from '@/components/Notebook/NotebookList.vue'
import ActivityConsole from '@/components/ActivityConsole.vue'
import PackageList from '@/components/Helium/PackageList.vue'

export default {
  name: 'LeftSideBar',
  components: {
    LeftNavBar,
    NotebookList,
    ActivityConsole,
    PackageList
  }
}
</script>

<style lang="scss" scoped>
.sidebar {
  display: flex;
  height: 100%;

  .sidebar-content {
    width: calc(100% - 40px);
    height: 100%;
    overflow-y: auto;
  }
}
</style>
