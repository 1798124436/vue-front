<template>
    <ul>
      <li v-for="(user) in users" :key="user.id">{{user.name}}</li>
    </ul>
</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
          users:[]
        };
    },
    created() {

    },
    mounted() {
      axios.get('http://localhost:3000/api/user').then(res =>{
        this.users = res.data
      })
    },
    methods: {

    }
};
</script>

<style scoped lang="scss">

</style>
