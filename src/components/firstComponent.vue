<template>
 <div id="app">
  <v-app id="inspire">
     <v-card>
        <v-responsive :aspect-ratio="16/9">
          <v-card-text>
    <v-toolbar>
        <!-- <v-text-field
            label="Title"/> -->
        <v-toolbar-title>{{Title}}</v-toolbar-title>
    </v-toolbar>
    <br><br>
    <form>
      <v-text-field
        v-model="name"
        :error-messages="nameErrors"
        :counter="10"
        label="Name"
        required
        @input="$v.name.$touch()"
        @blur="$v.name.$touch()"
      ></v-text-field>
      <v-text-field
        v-model="email"
        :error-messages="emailErrors"
        label="E-mail"
        required
        @input="$v.email.$touch()"
        @blur="$v.email.$touch()"
      ></v-text-field>
      <v-select
        v-model="select"
        :items="items"
        :error-messages="selectErrors"
        label="Item"
        required
        @change="$v.select.$touch()"
        @blur="$v.select.$touch()">
      </v-select>
    <v-file-input label="File input"></v-file-input>

      <v-switch
            v-model="shaped"
            class="ma-1"
            label="I agree all the above data is true"
            :enabled="!outlined && !filled && !solo">
       </v-switch>
      <v-checkbox
        v-model="checkbox"
        :error-messages="checkboxErrors"
        label="Do you agree?"
        required
        @change="$v.checkbox.$touch()"
        @blur="$v.checkbox.$touch()"
      ></v-checkbox>
  
      <v-btn class="mr-4" @click="submit">submit</v-btn>
      <v-btn @click="clear">clear</v-btn>
    </form>

    <v-footer>
      <div class="flex-grow-1"></div>
      <div>&copy; {{ new Date().getFullYear() }}</div>
    </v-footer>

       </v-card-text>
        </v-responsive>
      </v-card>
  </v-app>
</div>
</template>

<script>
export default {
    
}

</script>

<style scoped>
</style>