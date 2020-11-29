<template>
  <validation-provider
    v-slot="{ errors }"
    :name="name"
    :rules="rules"
    :vid="vid"
  >
    <v-text-field
      v-model="currentValue"
      :placeholder="placeholder"
      :type="type"
    />
    <span class="error--text">{{ errors[0] }}</span>
  </validation-provider>
</template>

<script lang="ts">
import { Component, Prop, Watch, Vue } from 'nuxt-property-decorator'
import { ValidationProvider } from 'vee-validate'

@Component({
  components: {
    ValidationProvider,
  },
})
export default class TextInput extends Vue {
  @Prop({ type: String, required: true, default: '' })
  name!: string

  @Prop({ type: String, default: '' })
  rules!: string

  @Prop({ type: String, default: undefined })
  vid!: string

  @Prop({ type: String, default: '' })
  placeholder!: string

  @Prop({ type: String, default: 'text' })
  type!: string

  // v-model変更時の振る舞い
  currentValue = ''
  @Watch('currentValue')
  updateCurrentValue(val: string) {
    this.$emit('input', val)
  }
}
</script>

<style scoped></style>
