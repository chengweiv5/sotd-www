<template>
  <ul class="list -component-events-detail-categoriessocial-categories">
    <li v-for="(category, index) in item.categories" :key="index" @click="$mixpanel.track('Event - Category')" class="item -category" :class="'--' + category">{{ category | formatEventCategory | capitalize }}</li>
  </ul>
</template>

<script>
  export default {
    computed: {
      item () {
        return this.$store.getters['events/detail/item']
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import '~assets/css/settings';

  .-category {
    &.item {
      padding-left: 20px;
      position: relative;
      font-size: 1.05rem;
      line-height: 1.3;
      margin-right: 12px;
      &:before {
        content: "";
        position: absolute;
        width: 15px;
        height: 15px;
        background-color: $color--black;
        left: 0;
        top: 1px;
        border-radius: 50%;
      }
      &.--ico {
        &:before {
          background: $color--event-ico;
        }
      }
      &.--hackathon {
        &:before {
          background: $color--event-hackathon;
        }
      }
      &.--summit {
        &:before {
          background: $color--event-summit;
        }
      }
      &.--crowdsale {
        &:before {
          background: $color--event-crowdsale;
        }
      }
      &.--conference {
        &:before {
          background: $color--event-conference;
        }
      }
      &.--meetup {
        &:before {
          background: $color--event-meetup;
        }
      }
      &.--release {
        &:before {
          background: $color--event-release;
        }
      }
      &.--workshop {
        &:before {
          background: $color--event-workshop;
        }
      }
    }
  }

  .-component-events-detail-categoriessocial-categories {
    &.list {
      margin: 5px 0 10px 0;
      display: flex;
      align-items: center;
      flex-direction: column;
      @include tweakpoint('min-width', 600px) {
        margin: 0;
        flex-grow: 1;
        flex-direction: row;
      }
    }
  }
</style>
