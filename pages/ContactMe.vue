<template>
  <div class="mt-16">
    <div class="section-heading text-center font-header">
      Get in touch
    </div>
    <div class="description text-center px-12">
      Do you have web development projects, freelance missions or just opportunities to offer me? Let's get in
      touch and discuss it over a coffee!
    </div>
    <div class="form px-16 mb-16">
      <v-form ref="form" v-model="valid" class="px-16">
        <v-row>
          <v-col md="6">
            <div class="label text-uppercase font-header">
              First Name
            </div>
            <v-text-field
              v-model="firstName"
              light
              placeholder="John"
              color="black"
              background-color="white"
              outlined
              filled
              class="mt-3"
              :rules="[(value) => (!!value && !!(value + '')?.length) || 'This field is required.']"
            />
          </v-col>
          <v-col md="6">
            <div class="label text-uppercase font-header">
              Last Name
            </div>
            <v-text-field
              v-model="lastName"
              light
              placeholder="Doe"
              color="black"
              background-color="white"
              outlined
              filled
              class="mt-3"
              :rules="[(value) => (!!value && !!(value + '')?.length) || 'This field is required.']"
            />
          </v-col>
        </v-row>
        <v-row>
          <v-col md="12">
            <div class="label text-uppercase font-header">
              Email
            </div>
            <v-text-field
              v-model="email"
              light
              placeholder="johndoe@gmail.com"
              color="black"
              background-color="white"
              outlined
              filled
              class="mt-3"
              :rules="[
                (value) => (!!value && !!(value + '')?.length) || 'This field is required.',
                (v) => !v?.length || !!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(v) || 'Email is invalid'
              ]"
            />
          </v-col>
        </v-row>
        <v-row>
          <v-col md="12">
            <div class="label text-uppercase font-header">
              Message
            </div>
            <v-textarea
              v-model="message"
              light
              placeholder="Your message"
              color="black"
              background-color="white"
              outlined
              filled
              class="mt-3"
              :rules="[(value) => (!!value && !!(value + '')?.length) || 'This field is required.']"
            />
          </v-col>
        </v-row>
        <v-row align="center" justify="center">
          <v-col class="text-center">
            <v-btn
              rounded
              color="#c7ff84"
              height="50"
              :disabled="(!valid) || loading"
              :loading="loading"
              @click="sendEmail()"
            >
              SEND
            </v-btn>
          </v-col>
        </v-row>
      </v-form>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'ContactMe',
  data: () => ({
    valid: false,
    firstName: '',
    lastName: '',
    email: '',
    message: '',
    loading: false
  }),
  methods: {
    sendEmail () {
      if (this.$refs.form.validate()) {
        const request = {
          firstName: this.firstName,
          lastName: this.lastName,
          email: this.email,
          message: this.message
        }
        this.loading = true
        axios.post(`https://db4wfjxjcwmc3kz7spj3ruqt540rymwi.lambda-url.ap-southeast-1.on.aws/?subject=PortfolioContact&reply=${this.email}`, request).then(() => {
          this.loading = false
          this.$snackbar.show({
            message: 'Hi, I received your message and will contact you ASAP. Thank you',
            color: 'green',
            timeout: 5000
          })
          this.$refs.form.reset()
        }).catch(() => {
          this.loading = false
          this.$snackbar.show({
            message: 'Oops, Something Went Wrong, Try again later...',
            color: 'red',
            timeout: 5000
          })
        })
      }
    }
  }
}
</script>

<style scoped>
.section-heading {
  color: #c7ff84;
  font-weight: 700;
  font-size: 3rem;
  margin-bottom: 1rem;
}

.description {
  font-size: 1.5rem;
  font-family: Overpass, system-ui, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, Helvetica Neue, Arial, Noto Sans, sans-serif, Apple Color Emoji, Segoe UI Emoji, Segoe UI Symbol, Noto Color Emoji;
  margin-bottom: 5rem;
}

.label {
  color: #c7ff84;
  font-size: 1.25rem;
  font-weight: 700;
}

.v-input {
  font-size: 1.125rem;
  color: #2d3748;
  font-family: Overpass, system-ui, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, Helvetica Neue, Arial, Noto Sans, sans-serif, Apple Color Emoji, Segoe UI Emoji, Segoe UI Symbol, Noto Color Emoji;
}

.v-btn {
  border: solid #e5fec7;
  font-size: 1.35rem;
  color: #394726;
  font-weight: 700;
}

::v-deep .v-btn__content {
  padding: 0.5rem 3rem;
}

@media (max-width: 768px) {
  .px-16 {
    padding-left: 0 !important;
    padding-right: 0 !important;
  }
}
</style>
