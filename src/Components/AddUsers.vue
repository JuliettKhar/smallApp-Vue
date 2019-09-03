<template>
  <div>
    <h2>Add users</h2>

    <div class="form-group">
      <label>Name</label>
      <input class="form-control" type="text" v-model="user.name" />
    </div>

    <div class="form-group">
      <label>Lastname</label>
      <input class="form-control" type="text" v-model="user.lastname" />
    </div>

    <button class="addUsers__btn" @click="submit">Submit</button>
  </div>
</template>


<script>
export default {
  data() {
    return {
      user: {
        name: "",
        lastname: ""
      },
      resourse: ""
    };
  },
  methods: {
    submit() {
      //   this.$http
      //     .post("http://localhost:3004/users", this.user)
      //     .then(response => {
      //       console.log(response);
      //     });

      this.resource.save({}, this.user).then(response => {
        console.log(response);
      });
    }
  },
  created() {
    this.resource = this.$resource("http://localhost:3004/users");
  }
};
</script>

<style >
.addUsers__btn {
  width: 150px;
  height: 30px;
  border-radius: 30px;
  line-height: 18px;
  background: #fff;
  border: 1px solid #e2031a;
  outline: none;
  cursor: pointer;
}

.addUsers__btn:hover {
  background: #e2031a;
  color: #fff;
}

.form-control {
  border: 1px solid rgba(68, 68, 68, 0.5);
  outline: none;
}
</style>