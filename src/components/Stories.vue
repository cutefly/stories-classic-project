<template>
  <ul class="list-group">
    <li v-for="story in stories" v-bind:key="story" class="list-group-item">
      {{ story.writer }} said "{{ story.plot }}"
      Story upvotes {{ story.upvotes }}.
    </li>
  </ul>
</template>

<script>
import {store} from '../store.js'

export default {
  data () {
    return {
      stories: store.stories
    }
  },

  created () {
    console.log('stories')
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
