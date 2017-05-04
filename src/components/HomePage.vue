<template>
  <div>
    <v-row>
      <v-col xs8 offset-xs2>
        <v-row>
          <v-col sm6 class="pa-4" v-for="d in demos" :key="d.url">
            <v-card>
              <v-card-text>
                <h5>{{d.title}}</h5>
                <h6>{{d.subtitle}}</h6>
                <v-btn primary @click.native="redirect(d.url)">
                  Live Demo
                </v-btn>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  data () {
    return {
      demos: [{
        title: 'Material Style',
        subtitle: 'Vuetify',
        url: '/vuetify-index.html'
      }, {
        title: 'Element',
        subtitle: 'Element',
        url: '/element-index.html'
      }]
    }
  },
  methods: {
    redirect (url) {
      window.location.href = url
    }
  }
}
</script>

<style scoped>
.card {
  margin: 0 auto;
  min-height: 200px;
  min-width: 200px;
}
h6 {
  color: #999;
}
</style>
