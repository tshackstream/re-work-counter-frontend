<template>
  <v-container>
    <validation-observer ref="obs" v-slot="{ invalid }">
      <v-row>
        <v-col>
          <text-input
            v-model="email"
            name="ID"
            placeholder="ID(メールアドレス)"
            rules="required"
          />
          <text-input
            v-model="password"
            name="パスワード"
            placeholder="パスワード"
            rules="required"
            type="password"
          />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <v-btn :disabled="invalid" @click="onSubmit">ログイン</v-btn>
        </v-col>
      </v-row>
    </validation-observer>
  </v-container>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
import { ValidationObserver } from 'vee-validate'
import TextInput from '~/components/atoms/TextInput.vue'

@Component({
  components: {
    TextInput,
    ValidationObserver,
  },
  layout: 'simple',
})
export default class login extends Vue {
  email = ''
  password = ''

  onSubmit() {
    alert('yes')
  }
}
</script>

<style scoped></style>
