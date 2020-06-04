<template>
      <div>
          <h5>
            {{meal.category}}
          </h5>
          <hr>
          <h3>{{meal.name}}</h3>
          {{meal.cost.students}} €<br>
          <div class="ci" v-for="ci in meal.contentInformation" :key="ci"><small>{{ci}}</small></div>

          <br>
          <b-btn-toolbar class="vote-btns">
              <b-button-group class="mr-1">
                <b-button title="upvote">
                  <b-icon-hand-thumbs-up v-on:click="vote(meal, 'up')" class="vote-icn"></b-icon-hand-thumbs-up>
                  ({{meal.upvotes}})
                </b-button>

                <b-button title="downvote">
                  <b-icon-hand-thumbs-down v-on:click="vote(meal, 'down')" class="vote-icn"></b-icon-hand-thumbs-down>
                  ({{meal.downvotes}})
                </b-button>
              </b-button-group>
            </b-btn-toolbar>
          <!--
          {{meal.cost}}
          {{meal.day}}
          {{meal.downvotes}}
          {{meal.id}}
          {{meal.labels}}
          {{meal.upvotes}}
          -->
          
      </div>
</template>

<script>
// import axios from 'axios'

export default {
  name: 'Mahlzeit',
  props: {
    meal: Object
  },
  methods: {
    vote(meal, vote) {
      this.$socket.emit('broadcastLike', meal.name, vote, 'von Marc')
      console.log(`${meal.name} [${meal.id}]: ${vote}`)
      /*
      axios.post("http://localhost:3000/api/vote", {
        mealId: meal.id,
        vote: vote
      })
      .catch(err => {
        console.log(err)
      });
      */
    }
  },
  sockets: {
    connect() {
      // Fired when the socket connects.
      console.log('connected')
    },

    disconnect() {
      console.log('disconnected')
    },

    // Fired when the server sends something on the "messageChannel" channel.
    messageChannel(data) {
      console.log('message-channel')
      console.log(data);
    }
  },
  mounted() {
    this.sockets.subscribe('broadcastLike', (data) => {
      console.log('like')
      console.log(data);
    });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.ci {
  font-size: 8pt;
  display: inline-block;
  margin-right: 10px;
}

.vote-btns {
  align-content: right;
}
</style>
