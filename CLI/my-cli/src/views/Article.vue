<template>
	<div>
		<div>記事コード: {{ aid }}</div>
		<span><router-link :to="'/article/' + aid + '/pages/1'">Page: 1</router-link></span>
		<span><router-link :to="'/article/' + aid + '/pages/2'">Page: 2</router-link></span>
		<router-view />
	</div>
</template>
<script>
let timeGuard = (to, from, next) => {
	let data = {
		13: new Date(2021, 2, 1),
		100: new Date(2020, 2, 1)
	}

	let limit = data[to.params.aid] ? data[to.params.aid] : new Date(2999, 12, 31)
	console.log(limit)
	let current = new Date()
	if (limit && limit.getTime() > current.getTime()) {
		console.log(to.params.aid)
		next()
	} else {
		window.alert('記事の公開期限がすぎています。')
		next('/')
	}

}
export default {
	name: 'Article',
	beforeRouteEnter: timeGuard,
	beforeRouteUpdate: timeGuard,
	props: {
		aid: String
	}
}
</script>


