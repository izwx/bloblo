<template>
<div class="js-recommended-followers dashboard-user-recommendations flex-module-inner" data-section-id="wtf" style="opacity: 1;">
  <div class="UserSmallListItem js-account-summary account-summary js-actionable-user" data-feedback-token="180" data-impression-id>
    <div class="UserSmallListItem-context">
    </div>
    <div class="dismiss js-action-dismiss"></div>
    <div class="content" v-for="account in follow_accs" :key="account.id" style="margin-bottom: 25px;">
      <a :href='"/u/"+account.username' class="account-group js-recommended-link js-user-profile-link user-thumb" >
        <img :src="account.avatar" class="avatar js-action-profile-avatar" />
        <span class="account-group-inner">
          <strong class="fullname">{{ account.display_name }}</strong>
          <span class="UserBadges"></span>
          <span class="UserNameBreak">&nbsp;</span>
          <span class="username u-dir u-textTruncate" dir="1tr">@{{ account.username }}</span>
        </span>
      </a>

    </div>
  </div>
</div>
</template>

<script>
import axios from 'axios';
export default {
  data() {
    return {
      follow_accs: []
    };
  },
  mounted() {
    var self = this;
    axios.get('http://192.168.44.128:9000/following_acc/')
    .then( function(res){
      self.follow_accs = res.data;
      console.log('Data: ',res.data);
    })
    .catch( function (error) {
      console.log('ERROR: ',error);
    })
  }
};
</script>

<style lang="sass" scoped>

</style>
