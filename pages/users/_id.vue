<template>
    <div>
        <!-- <h1>Hello user {{$route.params.id}}</h1> -->
        <h1>{{user.name}}</h1>
        <p>{{user.email}}</p>
        <p>{{user.phone}}</p>
        <NuxtLink to="/users">Back to Users</NuxtLink>
    </div>
</template>
<script>
export default {
    data(){
        return{
            user:{}
        };
    },
    created(){
    fetch(`https://jsonplaceholder.typicode.com/users/${this.$route.
    params.id}`)
  .then(response => response.json())
  .then(json => {
    this.user=json;
    // console.log(json);
  });
    }
};
</script>