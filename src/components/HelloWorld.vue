<template>
  <div class="col-full">
    <h1>Welcome</h1>
    <ThreadList :threads="threads"/>
  </div>
</template>

<script>

import sourceData from '@/data';
import ThreadList from './ThreadList'
console.log(sourceData);

export default {
  name: 'HelloWorld',

  components: {
    ThreadList
  },

  data () {
    return {
      threads: Object.values(sourceData.threads),
      posts: sourceData.posts,
      users: sourceData.users,
    }
  }
}
</script>


<style scoped>

.img-round, .avatar, .avatar-xsmall, .avatar-small, .avatar-medium, .avatar-large, .avatar-xlarge {
    border-radius: 50%;
    max-width: 100%;
}

.forum-list {
    padding: 0;
    background: white;
    margin: 20px 0;
}

.forum-list .forum-listing {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    padding: 20px 10px 20px 30px;
}

.forum-list .forum-listing:nth-child(odd) {
    background: rgba(73, 89, 96, 0.06);
    border-bottom-left-radius: 20px;
}

.forum-list .forum-listing:last-child {
    border-bottom-left-radius: 0;
}

.forum-list .forum-listing .forum-details {
    flex-basis: 52%;
}

@media (min-width: 240px) and (max-width: 720px) {
    .forum-list .forum-listing .forum-details {
        flex-basis: 100%;
    }
}

.forum-list .forum-listing .forum-details ul.subforums {
    padding-left: 5px;
    display: block;
}

.forum-list .forum-listing .forum-details ul.subforums::before {
    content: '⌙';
    margin-right: 5px;
}

.forum-list .forum-listing .forum-details ul.subforums.subforums li {
    display: inline;
}

.forum-list .forum-listing .forum-details ul.subforums.subforums li:not(:last-of-type)::after {
    content: '\f111';
    font-family: 'FontAwesome';
    font-size: 4px;
    position: relative;
    top: -3px;
    left: 2px;
    padding: 0 3px;
    color: #878787;
}

.forum-list .forum-listing .threads-count {
    flex-basis: 12%;
    text-align: center;
}

.forum-list .forum-listing .threads-count .count {
    font-weight: 100;
    display: block;
}

.forum-list .forum-listing .last-thread {
    flex-basis: 32%;
    display: flex;
    justify-content: flex-start;
    align-items: center;
}

.forum-list .forum-listing .last-thread .avatar {
    margin-right: 10px;
}
</style>
