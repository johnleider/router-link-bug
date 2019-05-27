<template>
  <div>
		<button @click="show = !show">Open</button>
    <router-link to="/" v-if="show">
      <input type="password">
    </router-link>
	</div>
</template>

<script>
  export default {
    data () {
      return {
        show: false
      }
    }
  }
</script>
