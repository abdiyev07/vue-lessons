<template>
  <div id="app">

    <LifecycleHooks v-if="isAlive" :title="title" />

    <button @click="destroyComponent"> Destroy </button>

    <!-- <Login v-if="isUserLogged" @success="userLogged" />
    <UserDetails :user="user" /> -->
    <!-- <div class="elements">
      <div v-for="post in posts" :key="post.id" class="element">Заголовок: {{ post.title }}</div>
    </div> -->
  </div>
</template>

<script>
import Login from "@/components/Login.vue";
import UserDetails from "@/components/UserDetails.vue";

export default {
	name: "App",

	data() {
		return {
			isUserLogged: false,
			user: {},
			isLoading: false,
			posts: [],
			title: "Title 1",
			isAlive: true
		};
	},

	// async created() {
	//   try {
	//     this.isLoading = true
	//     const response = await fetch('https://jsonplaceholder.typicode.com/posts')
	//     const data = await response.json()
	//     this.posts = data
	//   } catch (e) {
	//     console.log(e)
	//   } finally {
	//     this.isLoading = false
	//   }
	// },

	async mounted() {},

	beforeDestroy() {
		// У нас есть доступ к this
		// HTML элементы не удалены
	},

	destroyed() {
		// Компонент уже удален полностью
	},

	methods: {
		destroyComponent() {
			this.isAlive = false;
		},

		userLogged(user) {
			this.isUserLogged = true;
			this.user = user;
		}
	},

	components: {
		Login,
		UserDetails,
		LifecycleHooks: () => import("@/components/LifecycleHooks.vue")
	}
};
</script>

<style lang="scss">
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}

.input {
	padding: 0.6rem;
	margin-bottom: 1rem;
	width: 200px;
}
</style>
