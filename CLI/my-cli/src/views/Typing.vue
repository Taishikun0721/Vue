<template>
  <v-form v-model="valid">
    <v-container>
      <v-row>
		<v-col cols="12" md="12">
			<v-text-field v-model= "firstname" :rules="nameRules" :counter="10" label="first name" required></v-text-field>
		</v-col>
		<v-col cols="12" md="12">
			<v-text-field v-model= "lastname" :rules="nameRules" :counter="10" label="last name" required></v-text-field>
		</v-col>
		<v-col cols="12" md="12">
			<v-text-field v-model= "email" :counter="10" label="email" required></v-text-field>
		</v-col>
    <v-btn
      depressed
      color="primary"
      @click="submitData"
    >
      Primary
    </v-btn>
      </v-row>
    </v-container>
  </v-form>
</template>

<script>
export default {
    data: () => ({
      valid: false,
      firstname: '',
      nameRules: [
        v => !!v || 'Name is required',
		v => v.length <= 10 || 'Name must be less than 10 characters',
   ],
    lastname: '',
    email: '',
    personalData: []
	}),
	methods: {
		submitData() {
			this.personalData = [this.firstname, this.lastname, this.email]
			this.firstname = ''
			this.lastname = ''
			this.email = ''
		}
	}
}
</script>
