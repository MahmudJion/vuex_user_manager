<template>
 <form @submit.prevent="onUserSubmit">
  <div class="form-group">
    <input type="text" class="form-control" placeholder="Name" v-model="name">
  </div>
  <div class="form-group">
    <input type="text" class="form-control" placeholder="Email" v-model="email">
  </div>
  <button type="submit" class="btn btn-block btn-primary">Add</button>
</form>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: 'AddUser',
  data(){
      return {
        name: '',
        email: ''
      }
  },
  methods:{
    ...mapActions(["addUsers"]),
    onUserSubmit() {
        this.addUsers({
          name: this.name,
          email: this.email
        })
    }
  }
}
</script>