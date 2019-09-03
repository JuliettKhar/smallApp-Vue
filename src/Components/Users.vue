<template>
  <div>
    <h2>List of users</h2>

    <div class="user__item" v-for="(user, index) in users" :key="index">
      <div>
        <span class="user__title">Name:</span>
        {{ user.name }}
      </div>
      <div>
        <span class="user__title">Lastname:</span>
        {{ user.lastname }}
      </div>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      users: "",
      resource: ""
    };
  },
  methods: {
    fetchData() {
      //   this.$http.get("http://localhost:3004/users").then(response => {
      //     this.users = response.body;
      //   });
      this.resource.get().then(response => {
        this.users = response.body;
      });
    }
  },
  created() {
    this.resource = this.$resource("http://localhost:3004/users");
    this.fetchData();
  }
};
</script>

<style>
.user__item {
  box-sizing: border-box;
  border: 1px solid rgba(68, 68, 68, 0.5);
  width: 250px;
  padding: 20px;
  float: left;
  margin-left: 10px;
  background: #f7f7f7;
  margin-bottom: 10px;
}

.user__title {
  font-weight: 700;
}
</style>