<template>
    <div>

        <div class="columns">
            <div class="column">
                <table class="table">
                    <tr v-for="listuser in users" :key="listuser.id" @click="selectedUser(listuser.id)">
                        <td>{{ listuser.name }}</td>
                        <td>{{ listuser.email }}</td>
                    </tr>
                </table>
                <button @click="getUser()">CLICK</button>
            </div>
            <selectuser :selectuser="selectUser" />
        </div>

    </div>
</template>

<script>
import axios from "axios";
//import users from "../users.json";
import selectUser from "./SelectUser";

export default {
  data() {
    return {
      users: [],
      selectedUserId: 0
    };
  },
  components: {
    selectuser: selectUser
  },
  computed: {
    selectUser() {
      return this.users.find(each => {
        return each.id === this.selectedUserId;
      });
    }
  },
  methods: {
    selectedUser(id) {
      this.selectedUserId = id;
    },

    getUser() {
      axios.get("https://jsonplaceholder.typicode.com/users").then(res => {
        console.log(res.data);
        this.users = res.data;
      });
    }
  }
};
</script>

<style scoped>
tr {
  cursor: pointer;
}
.box {
  color: #fff;
  background: #000;
}
</style>
