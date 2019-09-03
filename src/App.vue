<template>
  <div>
    <Header />
    <div class="container">
      <div>
        <button class="users__btn" @click="active = 'Users'">Users</button>
        <button class="addUsers__btn" @click="active = 'AddUsers'">Add users</button>
      </div>
      <hr />

      <div>
        <component :is="this.active"></component>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from "./Components/Header_footer/Header.vue";
import Footer from "./Components/Header_footer/Footer.vue";
import Users from "./Components/Users.vue";
import AddUsers from "./Components/AddUsers.vue";

export default {
  data() {
    return {
      active: "Users"
    };
  },
  components: {
    Users,
    AddUsers,
    Header,
    Footer
  }
};
</script>

<style  scoped>
body {
  margin: 0;
  padding: 0;
  font-family: "Gayathri", sans-serif;
  color: #444;
}

.container {
  box-sizing: border-box;
  padding: 20px;
  min-height: 84vh;
}

.users__btn,
.addUsers__btn {
  width: 150px;
  height: 30px;
  border-radius: 30px;
  line-height: 25px;
  background: #fff;
  border: 1px solid #e2031a;
  outline: none;
  cursor: pointer;
}

.users__btn:hover,
.addUsers__btn:hover {
  background: #e2031a;
  color: #fff;
}

.users__btn {
  margin-right: 30px;
}
</style>