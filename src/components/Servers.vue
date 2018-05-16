<template>
  <ul class="list-group">
    <li v-for="server in servers" v-bind:key="server" class="list-group-item">
      {{ server.seq }} {{ server.url }} {{ server.valid}} {{ server.use_flag}} {{ server.sender}} {{ server.receiver}}
    </li>
  </ul>
</template>

<script>
import {store} from '../servers.js'

export default {
  data () {
    return {
      servers: store.servers
    }
  },

  created () {
    console.log('servers')
  }
/*
    props: ['stories']

    data () {
      return {
        stories: [
          {
            plot: 'My horse is amazing.',
            writer: 'Mr. Weebl',
            upvotes: 28,
            voted: false
          },
          {
            plot: 'Narwhals invented Shish Kebab.',
            writer: 'Mr. Weebl',
            upvotes: 8,
            voted: false
          },
          {
            plot: 'The dark side of the Force is stronger.',
            writer: 'Darth Bader',
            upvotes: 52,
            voted: false
          },
          {
            plot: 'One does not simply walk into Mordor',
            writer: 'Boromir',
            upvotes: 74,
            voted: false
          }
        ]
      }
    }
*/
}
</script>
