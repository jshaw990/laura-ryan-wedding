<template>
  <v-container>
    <v-card v-if="!submitted" class="py-8" color="rgba(92, 20, 39, .75)">
      <v-form
        v-if="!loading"
        class="w-full pa-4 text-center"
        autocomplete="off"
        v-model="isValid"
      >
        <v-row v-if="peopleAttending === 0" justify="space-between">
          <v-select
            :items="range"
            label="Number of Guests Invited"
            v-model="peopleAttending"
            class="mx-md-8 mx-2 sm-mx-0 text-center"
            color="white"
          />
        </v-row>
        <v-row
          v-if="peopleAttending !== 0"
          justify="space-between"
          class="my-md-4 my-2"
        >
          <v-col cols="12" md="4">
            <v-text-field
              v-model="form.attendee[0].name"
              label="Guest Name"
              class="mx-md-4 mx-2 sm-mx-0 text-center"
              autocomplete="new-password"
              color="white"
              required
            />
          </v-col>
          <v-col cols="12" md="4">
            <v-text-field
              v-model="form.attendee[0].dietary"
              label="Dietary Restriction"
              class="mx-md-4 mx-2 sm-mx-0 text-center"
              autocomplete="new-password"
              color="white"
            />
          </v-col>
          <v-col cols="12" md="4">
            <v-select
              :items="attendingOptions"
              label="Does this guest accept this invitation?"
              v-model="form.attendee[0].attending"
              class="mx-md-4 mx-2 sm-mx-0 text-center flex-grow-0"
              color="white"
            />
          </v-col>
        </v-row>
        <v-row
          v-if="peopleAttending > 1"
          justify="space-between"
          class="my-md-4 my-2"
        >
          <v-col cols="12" md="4">
            <v-text-field
              v-model="form.attendee[1].name"
              label="Guest Name"
              class="mx-md-4 mx-2 sm-mx-0 text-center"
              autocomplete="new-password"
              color="white"
              required
            />
          </v-col>
          <v-col cols="12" md="4">
            <v-text-field
              v-model="form.attendee[1].dietary"
              label="Dietary Restriction"
              class="mx-md-4 mx-2 sm-mx-0 text-center"
              autocomplete="new-password"
              color="white"
            />
          </v-col>
          <v-col cols="12" md="4">
            <v-select
              :items="attendingOptions"
              label="Does this guest accept this invitation?"
              v-model="form.attendee[1].attending"
              class="mx-md-4 mx-2 sm-mx-0 text-center flex-grow-0"
              color="white"
            />
          </v-col>
        </v-row>
        <v-row
          v-if="peopleAttending > 2"
          justify="space-between"
          class="my-md-4 my-2"
        >
          <v-col cols="12" md="4">
            <v-text-field
              v-model="form.attendee[2].name"
              label="Guest Name"
              class="mx-md-4 mx-2 sm-mx-0 text-center"
              autocomplete="new-password"
              color="white"
              required
            />
          </v-col>
          <v-col cols="12" md="4">
            <v-text-field
              v-model="form.attendee[2].dietary"
              label="Dietary Restriction"
              class="mx-md-4 mx-2 sm-mx-0 text-center"
              autocomplete="new-password"
              color="white"
            />
          </v-col>
          <v-col cols="12" md="4">
            <v-select
              :items="attendingOptions"
              label="Does this guest accept this invitation?"
              v-model="form.attendee[2].attending"
              class="mx-md-4 mx-2 sm-mx-0 text-center flex-grow-0"
              color="white"
            />
          </v-col>
        </v-row>
        <v-row
          v-if="peopleAttending > 3"
          justify="space-between"
          class="my-md-4 my-2"
        >
          <v-col cols="12" md="4">
            <v-text-field
              v-model="form.attendee[3].name"
              label="Guest Name"
              class="mx-md-4 mx-2 sm-mx-0 text-center"
              autocomplete="new-password"
              color="white"
              required
            />
          </v-col>
          <v-col cols="12" md="4">
            <v-text-field
              v-model="form.attendee[3].dietary"
              label="Dietary Restriction"
              class="mx-md-4 mx-2 sm-mx-0 text-center"
              autocomplete="new-password"
              color="white"
            />
          </v-col>
          <v-col cols="12" md="4">
            <v-select
              :items="attendingOptions"
              label="Does this guest accept this invitation?"
              v-model="form.attendee[3].attending"
              class="mx-md-4 mx-2 sm-mx-0 text-center flex-grow-0"
              color="white"
            />
          </v-col>
        </v-row>
        <v-row
          v-if="peopleAttending > 4"
          justify="space-between"
          class="my-md-4 my-2"
        >
          <v-col cols="12" md="4">
            <v-text-field
              v-model="form.attendee[4].name"
              label="Guest Name"
              class="mx-md-4 mx-2 sm-mx-0 text-center"
              autocomplete="new-password"
              color="white"
              required
            />
          </v-col>
          <v-col cols="12" md="4">
            <v-text-field
              v-model="form.attendee[4].dietary"
              label="Dietary Restriction"
              class="mx-md-4 mx-2 sm-mx-0 text-center"
              autocomplete="new-password"
              color="white"
            />
          </v-col>
          <v-col cols="12" md="4">
            <v-select
              :items="attendingOptions"
              label="Does this guest accept this invitation?"
              v-model="form.attendee[4].attending"
              class="mx-md-4 mx-2 sm-mx-0 text-center flex-grow-0"
              color="white"
            />
          </v-col>
        </v-row>
        <v-row
          v-if="peopleAttending > 5"
          justify="space-between"
          class="my-md-4 my-2"
        >
          <v-col cols="12" md="4">
            <v-text-field
              v-model="form.attendee[5].name"
              label="Guest Name"
              class="mx-md-4 mx-2 sm-mx-0 text-center"
              autocomplete="new-password"
              color="white"
              required
            />
          </v-col>
          <v-col cols="12" md="4">
            <v-text-field
              v-model="form.attendee[5].dietary"
              label="Dietary Restriction"
              class="mx-md-4 mx-2 sm-mx-0 text-center"
              autocomplete="new-password"
              color="white"
            />
          </v-col>
          <v-col cols="12" md="4">
            <v-select
              :items="attendingOptions"
              label="Does this guest accept this invitation?"
              v-model="form.attendee[5].attending"
              class="mx-md-4 mx-2 sm-mx-0 text-center flex-grow-0"
              color="white"
            />
          </v-col>
        </v-row>
        <div v-if="peopleAttending >= 1">
          <div class="text-left mx-md-4">Group contact information:</div>
          <v-row justify="space-between" cols="12" md="8" class="my-md-4 my-2">
            <v-text-field
              label="Phone Number"
              class="mx-md-8 mx-2 sm-mx-0 text-center"
              v-model="form.phone"
              :rules="[
                () => !!form.phone || 'Phone Number is required',
                () =>
                  (!!form.phone && form.phone.length === 10) ||
                  'Phone Number must be 10 digits.',
              ]"
              counter="10"
              autocomplete="new-password"
              color="white"
              required
            />
            <v-text-field
              label="Email Address"
              class="mx-md-8 mx-2 sm-mx-0 text-center"
              v-model="form.email"
              autocomplete="new-password"
              :rules="[() => !!form.email || 'Email Address is required']"
              color="white"
              required
            />
          </v-row>
          <v-radio-group
            label="Can we text you important wedding updates?"
            class="text-center"
            v-model="form.canContact"
            color="white"
            required
          >
            <v-row justify="space-between" cols="12" md="6" class="ma-8">
              <v-radio value="Yes" label="Yes" color="white" />
              <v-radio value="No" label="No" color="white" />
            </v-row>
          </v-radio-group>
          <div class="text-center mb-8" v-if="isValid">
            <v-btn large color="rgba(92, 20, 39, 1)" @click="submitForm"
              >Submit RSVP Form</v-btn
            >
          </div>
          <div class="text-center mb-8" v-if="!isValid">
            <v-btn
              large
              color="rgba(92, 20, 39, 1)"
              @click="submitForm"
              disabled
              >Submit RSVP Form</v-btn
            >
          </div>
        </div>
      </v-form>
      <v-row v-else justify="center" align="center" class="py-12">
        <v-progress-circular indeterminate color="white"></v-progress-circular
      ></v-row>
    </v-card>
    <v-card
      v-else-if="!loading && submitted"
      class="py-md-8 pa-8"
      color="rgba(92, 20, 39, .75)"
    >
      <v-col v-if="success" cols="12" class="my-md-4 my-2 text-center">
        <RsvpSuccess :attendee="form.attendee" />
      </v-col>
      <v-col v-else cols="12" class="my-md-4 my-2 text-center">
        <RsvpFailure :error="error" />
      </v-col>
    </v-card>
    <v-card v-else class="py-md-8 pa-8" color="rgba(92, 20, 39, .75)">
      <v-row justify="center" align="center" class="py-12">
        <v-progress-circular indeterminate color="white"></v-progress-circular
      ></v-row>
    </v-card>
  </v-container>
</template>

<script>
import { reactive, toRefs } from '@vue/composition-api'

import RsvpSuccess from '@/components/RsvpSuccess.vue'
import RsvpFailure from '@/components/RsvpFailure.vue'

const FORMSPARK_URL = 'https://submit-form.com/rdYmiPpw'

export default {
  name: 'RSVP',
  components: {
    RsvpSuccess,
    RsvpFailure,
  },
  setup(props, context) {
    const state = reactive({
      error: null,
      loading: false,
      isValid: false,
      submitted: false,
      success: false,
      peopleAttending: 0,
      range: [1, 2, 3, 4, 5, 6],
      attendingOptions: ['Graciously accepts', 'Regretfully declines'],
      form: {
        attendee: [
          {
            name: '',
            dietary: '',
            attending: '',
          },
          {
            name: '',
            dietary: '',
            attending: '',
          },
          {
            name: '',
            dietary: '',
            attending: '',
          },
          {
            name: '',
            dietary: '',
            attending: '',
          },
          {
            name: '',
            dietary: '',
            attending: '',
          },
          {
            name: '',
            dietary: '',
            attending: '',
          },
        ],
        phone: '',
        email: '',
        canContact: 'Yes',
      },
    })

    const submitForm = () => {
      state.loading = true
      state.submitted = true

      const attendees = []

      for (let i = 0; i < state.form.attendee.length; i++) {
        if (state.form.attendee[i].name !== '') {
          if (state.form.attendee[i].dietary === '') {
            state.form.attendee[i].dietary = 'None'
          }

          attendees.push(state.form.attendee[i])
        }
      }

      if (attendees.length !== 0) {
        const date = new Date()
        const time = date.getUTCDate()
        const sendEmail = async () => {
          await fetch(FORMSPARK_URL, {
            method: 'POST',
            headers: {
              'Content-Type': 'application/json',
              Accept: 'application/json',
            },
            body: JSON.stringify({
              'Wedding RSVP from': state.form.attendee[0].name,
              'Received at': time,
              'Number of people attending': state.peopleAttending,
              'Willing to be contacted': state.form.canContact,
              'Phone number': state.form.phone,
              Email: state.form.email,
              'Attendee 1': [
                {
                  Name: state.form.attendee[0].name,
                  'Dietary restriction': state.form.attendee[0].dietary,
                  'Attending response': state.form.attendee[0].attending,
                },
              ],
              'Attendee 2': [
                {
                  Name: state.form.attendee[1].name,
                  'Dietary restriction': state.form.attendee[1].dietary,
                  'Attending response': state.form.attendee[1].attending,
                },
              ],
              'Attendee 3': [
                {
                  Name: state.form.attendee[2].name,
                  'Dietary restriction': state.form.attendee[2].dietary,
                  'Attending response': state.form.attendee[2].attending,
                },
              ],
              'Attendee 4': [
                {
                  Name: state.form.attendee[3].name,
                  'Dietary restriction': state.form.attendee[3].dietary,
                  'Attending response': state.form.attendee[3].attending,
                },
              ],
              'Attendee 5': [
                {
                  Name: state.form.attendee[4].name,
                  'Dietary restriction': state.form.attendee[4].dietary,
                  'Attending response': state.form.attendee[4].attending,
                },
              ],
              'Attendee 6': [
                {
                  Name: state.form.attendee[5].name,
                  'Dietary restriction': state.form.attendee[5].dietary,
                  'Attending response': state.form.attendee[5].attending,
                },
              ],
            }),
          })
            .then(() => {
              state.success = true
              state.loading = false
            })
            .catch((error) => {
              console.error(error)
              state.success = false
              state.error = error
              state.loading = false
            })
        }

        sendEmail()
      } else {
        state.success = false

        state.error = 'Email failed to send'
        state.loading = false
      }
    }

    return {
      submitForm,
      ...toRefs(state),
    }
  },
}
</script>

<style lang="scss" scoped>
.my-md-4 my-2 {
  margin: 15px 0;
  padding: 10px 0;
}
</style>
