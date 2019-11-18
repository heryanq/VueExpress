<template>
  <div>
    <v-container padding fluid>
      <v-row align="center" justify="center">
        <v-col cols="12" sm="8" md="4">
          <v-card class="elevation-12">
            <v-toolbar
              color="primary"
              dark
              flat>
              <v-toolbar-title>
                Register
              </v-toolbar-title>
              <v-spacer />
            </v-toolbar>
            <v-card-text>
              <v-form>
                <v-text-field
                  label="Email"
                  name="email"
                  prepend-icon="email"
                  type="text"/>
              
                <v-text-field
                  id="password"
                  label="Password"
                  name="password"
                  prepend-icon="lock"
                  type="password"/>
                <br>
                <div class="danger-alert" v-html="error" />
                <br>
              </v-form>
            </v-card-text>
            <v-card-actions>
              <v-spacer />
              <v-btn
                class="v-btn v-btn--rounded v-btn--loading theme--light elevation-0 v-size--large accent-4"
                dark
                @click="login">
                Register
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  methods: {
    logout () {
      this.$store.dispatch('setToken', null)
      this.$store.dispatch('setUser', null)
      this.$router.push({
        name: 'songs'
      })
    }
  }
}
</script>

<style scoped>
.container.fluid{
  max-width: 50%;
}
.home {
  cursor: pointer;
}
.home:hover {
  color: red;
}
.padding {
  padding-top: 200px;
  padding-right: 50px;
  padding-bottom: 0px;
  padding-left: 50px;
}
</style>