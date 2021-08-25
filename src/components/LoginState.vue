<template>
  <div>
    <q-btn
      v-if="!loggedIn"
      class="text-grey-3 bg-grey-4"
      dense
      round
      unelevated
      icon="person"
      to="/user/login"/>
    <q-btn
      v-if="loggedIn"
      class=""
      flat
      :dense="$q.screen.lt.md"
      :round="$q.screen.lt.md">
      <q-avatar
        :size="$q.screen.lt.md? 'lg' : 'xl'">
        <q-img :src="avatar"/>
      </q-avatar>
      <div class="q-pl-sm gt-sm text-body1">
        {{ username }}
      </div>
      <q-menu
        fit>
        <q-list>
          <q-item
            clickable
            v-close-popup
            @click="logout">
            <q-item-section>
              <q-item-label>注销</q-item-label>
            </q-item-section>
          </q-item>
        </q-list>
      </q-menu>
    </q-btn>
  </div>
</template>

<script>
import axios from "axios";
import {defineComponent} from "vue";

export default defineComponent({
  name: "LoginState",
  data() {
    return {
      loggedIn: false,
      avatar: null,
      username: null
    }
  },
  created() {
    if (this.$q.cookies.has("userData")) {
      axios({
        method: 'get',
        url: '/api/info',
        withCredentials: true
      }).then((response) => {
        if (response.status === 200) {
          let info = response.data.data;
          this.loggedIn = true;
          this.avatar = info["headUrl"];
          this.username = info.userName;
        }
      }).catch((error) => {
        console.log(error.response);
      });
    }
  },
  methods: {
    logout() {
      axios({
        method: 'get',
        url: '/api/logout',
        withCredentials: true
      }).then((response) => {
        if (response.status === 200) {
          this.$q.notify({
            color: 'green',
            textColor: 'white',
            icon: 'cloud_done',
            message: '注销成功'
          });
          this.avatar = null;
          this.username = null;
          this.loggedIn = false;
          this.$router.replace({
            path: '/user/login',
          });
        }
      }).catch((error) => {
        if (error.status === 404) {
          this.$q.notify({
            color: 'amber',
            textColor: 'white',
            icon: 'warning',
            message: '注销失败，清空过期登录信息'
          });
          this.avatar = null;
          this.username = null;
          this.loggedIn = false;
          this.$router.replace({
            path: '/user/login',
          });
        } else {
          console.log(error.response);
        }
      });
    }
  },
  watch: {
    $route() {
      axios({
        method: 'get',
        url: '/api/info',
        withCredentials: true
      }).then((response) => {
        if (response.status === 200) {
          let info = response.data.data;
          this.loggedIn = true;
          this.avatar = info["headUrl"];
          this.username = info.userName;
        }
      }).catch((error) => {
        console.log(error.response);
      });
    }
  }
});
</script>

<style scoped>

</style>
