<template>
    <div>
        <v-layout>
            <v-flex xs12 sm6 offset-sm3>
                <v-card v-for="task in tasks" :key="task.id"  class="mb-1">
                    <v-card-media src="http://via.placeholder.com/400x200" height="200px">
                    </v-card-media>
                    <v-card-title primary-title>
                        <div>
                            <h3 class="headline mb-0">Card</h3>
                            <div>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Corporis dignissimos doloribus, enim et fuga id laboriosam natus odio sed sit tempora voluptatibus? Assumenda at cumque eum laboriosam nostrum pariatur sit?</div>
                        </div>
                    </v-card-title>
                    <v-card-actions>
                        <v-btn flat color="orange">Share</v-btn>
                        <v-btn flat color="orange">Explore</v-btn>
                    </v-card-actions>
                </v-card>
            </v-flex>
        </v-layout>
    </div>
</template>

<style>

</style>

<script>

import { mapGetters } from 'vuex'
import * as actions from '../store/action-types'

export default {
  name: 'Tasks',
  computed: {
    ...mapGetters(['tasks'])
  },
  mounted () {
    this.$store.dispatch(actions.FETCH_TASKS)
  }
}
</script>
