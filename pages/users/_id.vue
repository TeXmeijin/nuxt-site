<template>
    <div>
        <h1>ユーザID: {{ this.$route.params.id }}</h1>
        <h1>ユーザID: {{ user.name }}</h1>
    </div>
</template>

// ユーザー情報を格納
<script>
export default {
    data(){
        return {
            id: this.$route.params.id,
            users: [
                { 
                    id: 1, name: 'John Doe'
                },
                {
                    id: 2, name: 'Kevin Smith',
                },
                {
                    id: 3, name: 'Harry Bosch'
                },
            ],
        }
    },
    computed:{
        user(){
            return this.users.find(user => user.id == this.id);
        } 
    }
}
</script>

// ページタイトルにユーザー名を表示
<script>
    export default {
  head(){
    return{
      title: this.user.name,
    }
  },
  data(){
    return {
      id: this.$route.params.id,
      users: [
        { 
            id: 1, name: 'John Doe'
        },
　//中略
      ],
    }
  },
  computed:{
    user(){
      return this.users.find(user => user.id == this.id);
    } 
  }
}
</script>
