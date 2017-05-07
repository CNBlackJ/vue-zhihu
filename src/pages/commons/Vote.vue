<template lang="html">
  <div class="vote">
    <a v-show="!isShowAll" v-on:click="addVote">
      <div class="topic-vote">
        <span>
          {{ vote }}
        </span>
      </div>
    </a>

    <a v-show="isShowAll" v-on:click="addVote">
      <div class="topic-vote">
        <i class="fa fa-caret-up"></i>
      </div>
    </a>

    <div v-show="isShowAll" class="topic-vote">
      <span>
        {{ vote }}
      </span>
    </div>

    <a v-show="isShowAll" v-on:click="subVote">
      <div class="topic-vote">
        <i class="fa fa-caret-down"></i>
      </div>
    </a>
  </div>
</template>

<script>
export default {
  data () {
    return {
      vote: 0
    }
  },
  props: ['isShowAll'],
  methods: {
    addVote: function () {
      this.vote += 1
    },
    subVote: function () {
      this.vote -= 1
    }
  }
}
</script>

<style lang="css">
</style>
