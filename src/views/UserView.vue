<template>
  <div class="d-flex" v-for="userdata in users" :key="userdata">
    <users :user="userdata"></users>
  </div>
</template>

<script>
import usersData from '@/assets/users.json'
import users from '@/components/UserInfo.vue'

export default {
    name:'UserView',

    components: {
        users
    },

    data(){
        return {
            users: usersData
        }
    }
}
</script>

<style>

</style>