<template>
<section>
<div class="splash content">
  <img class="test" src="./assets/herbivore-large.svg">
  <h1 class="title">Welcome to Herbivore</h1>

  <div class="subtitle is-5 sub">
    A tool that lets you take a deeper look at the packets traveling through your networks.
    </br>
    Go checkout whats happening on your current network.
    <a>  <span @click="goRight" class="icon">
        <i class="fa fa-arrow-right highlight" aria-hidden="true"></i>
      </span>
    </a>
  </div>
  <div @click="goAbout" class='button'> About Herbivore </div>
  <p class="subtitle is-5 hint">
  Hint: you can also use the ← and → arrow keys to navigate.
  </p>
</div>
</section>
</template>
<script type="text/javascript">
import { mapGetters, mapActions } from 'vuex'
export default {
  data () {
    return {
      test: '1111',
      show: false
    }
  },
  computed: mapGetters({
    view: 'view'
  }),
  methods: {
    goRight: function () {
      this.incViewIndex()
      this.$router.push({
        path: `/${this.view.names[this.view.index]}`
      })
    },
    goAbout: function () {
      this.$router.push({
        path: `/about`
      })
    },
    ...mapActions([
      'incViewIndex',
      'newMessage',
      'newNotification'
    ])}
}

</script>
<style scoped>
.sub {
  margin: auto 0;
}
.hint {
    font-size: 1.1rem;
    font-weight: 100;
    line-height: 1.25;
    margin-top: 6em;
}
.highlight{
  color: #00d1b2;
}
  code {
    background-color: rgba(40, 56, 76, .5);
    border-radius: 3px;
    color: #fff;
    font-weight: bold;
    padding: 3px 6px;
    margin: 0 3px;
    vertical-align: bottom;
  }
  .test{
    width:256px;
    height: auto;
  }
  .splash {
    padding-top: 10%;
  }
</style>
