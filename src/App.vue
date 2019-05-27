<template>
  <div>
    <router-link to="/" v-if="show">
      Router Link
      <input type="password">
    </router-link>

    <div></div>

    <test v-if="show" @click="click">
      Custom component w/ Render FN
      <input type="password">
    </test>
	</div>
</template>

<script>
  export default {
    components: {
      Test: {
        methods: {
          click () {}
        },

        render (h) {
          return h('div', {
            on: {
              click: this.click
            }
          }, this.$slots.default)
        }
      }
    },

    data () {
      return {
        show: false
      }
    },

    mounted () {
      setInterval(() => {
        this.show = !this.show
      }, 2000)
    },

    methods: {
      click () {}
    }
  }
</script>
