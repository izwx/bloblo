<template>
<div id="app">
  <notifications group="app-errors" :duration="-1"></notifications>
  <notifications group="app-message" :duration="10000"></notifications>
  <alerts ref="alerts"></alerts>
  <div id="page-outer">
    <div class="AppContent wrapper wrapper-home" id="page-container" style="margin-top: -80px;">
      <div class="dashboard dashboard-left" style="margin-left: -31px;margin-top:5px;">
        <demo :account="account"></demo>
      </div>
      <div class="content-main top-timeline-tweetbox" id="timeline" role="main" aria-labelledby="content-main-heading" tabindex="-1" style="margin-left: 40px;margin: 60px;">
        <common></common>
        <div class="stream-container conversations-enabled js-request-more-stream-items">
          <div class="stream">
            <ol class="stream-items js-navigable-stream" id="stream-items-id">
              <li class="js-stream-item" id="stream-item-tweet-1078138020581130245" data-item-type="tweet">
                <messages-list :messages="[]" ref="messagesList"></messages-list>
              </li>
            </ol>
          </div>
        </div>
      </div>
      <div class="dashboard dashboard-right">
        <div class="module wtf-module js-wtf-module roaming-module has-content">
          <div class="flex-module" style="margin-top: 60px;">
            <div class="flex-module-header">
              <h3>Who following</h3>
              <small>.</small>
              <small class="view-all">
                <a class="js-view-all-link-nav" href="#" data-element-term="view_all_link">View all</a>
                <user_following :account="account"></user_following>
              </small>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
import NavTop from '../components/shared/_nav_top';
export default {
  props: [
    'account',
    'messages'
  ],
  data() {
    return {
      currentAccount: window.currentAccount
    }
  },
  methods: {
    addMessage(message) {
      // do something
    }
  },
  mounted() {
  }
}
</script>

<style lang="scss" scoped>
.change-left{
  margin-left: -70px;
}
.change-size {
  height: 240px;
  resize: none;
}

.down-top{
  margin-top: 50px;
}
</style>
