<template>
  <div>
    <ul>
      <li
        v-for="user in users"
        :key="user.userId"
      >
        <span class="user-id">{{ user.userId }}</span>
        <span class="user-name">{{ user.userName }}</span>
        <input type="text">
        <button @click="onClickRemove(index)">X</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'ListItem',
  data() {
    return {
      users: [
        {
          userId: 1,
          userName: 'Taro',
        },
        {
          userId: 2,
          userName: 'Jiro',
        },
        {
          userId: 3,
          userName: 'Saburo',
        },
        {
          userId: 4,
          userName: 'Shiro',
        },
      ]
    }
  },
  methods: {
    onClickRemove(index) {
      this.users.splice(index, 1);
    }
  }
}
</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
  width: 100%;
  max-width: 400px;
  margin: auto;
}
li {
  display: block;
  margin: 0 10px;
  text-align: left;
}
.user-id {
  display: inline-block;
  width: 30px;
}
.user-name {
  display: inline-block;
  width: 100px;
}
</style>
