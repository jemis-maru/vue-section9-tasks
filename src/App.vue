<template>
  <div class="mainDiv">
    <the-header></the-header>
    <badge-list></badge-list>
    <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info>
    <temp-list>
      <template #default="slotProps">
        <span>{{ slotProps.otherProp }}</span>
        <span><h3>{{ slotProps.item }}</h3></span>
        <span>{{ slotProps.otherProp }}</span>
      </template>
    </temp-list>
    <section class="btnSec">
      <div>
        <button @click="changeComponent('list-data')">User data</button>
        </div>
      <div>
        <button @click="changeComponent('list-content')">List</button>
      </div>
    </section>
    <keep-alive>
      <component :is="defaultComponent"></component>
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import BadgeList from './components/BadgeList.vue';
import UserInfo from './components/UserInfo.vue';
import TempList from './components/TempList.vue';
import ListData from './components/ListData.vue';
import ListContent from './components/ListContent.vue';

export default {
  components: {
    'the-header': TheHeader,
    'badge-list': BadgeList,
    'user-info': UserInfo,
    'temp-list': TempList,
    'list-data': ListData,
    'list-content': ListContent,
  },
  data() {
    return {
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
      defaultComponent: 'list-data',
    };
  },
  methods: {
    changeComponent(compo){
      this.defaultComponent = compo;
    },
  },
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.btnSec {
  margin: 2rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  display: flex;
  justify-content: space-between;
}
</style>