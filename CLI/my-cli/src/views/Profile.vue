<template>
	<div id="profile">
		<v-container class="text-center">
			<h1>This is a Profile</h1>
			<div class="d-flex justify-center align-center my-5">
				<v-avatar class="my-5 mx-3">
					<img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John">
				</v-avatar>
				<h3>{{ FullName }}</h3>
			</div>
			<div id="items">
				<v-card elevation="2" title>
					<v-card-ttitle>
						紹介文
					</v-card-ttitle>
					<v-card-text>
						{{ text }}
					</v-card-text>
					<v-card-actiond class="mx-5">
						<router-link to="/about">go to datail</router-link>
					</v-card-actiond>
					<v-card-actiond>
						<router-link to="/about">go to about</router-link>
					</v-card-actiond>
				</v-card>
			</div>
		</v-container>
	</div>
</template>

<script>
export default {
	data: () => {
		return {
			FullName: 'Inokuchi Taishiro',
			text: 'プログラミングが好きです。',
		}
	}
}
</script>
