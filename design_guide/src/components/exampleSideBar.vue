<template>
	<div id="sidebar">
		<ul class="examplemainList">
			<router-link tag="li" active-class="active" to="/" exact>Datamap设计规范</router-link>
			<router-link tag="li" active-class="active" to="/vi" exact>VI规范</router-link>
			<li>界面设计规范</li>
			<ul class="examplesubList">
				<li>界面布局</li>
				<router-link tag="li" active-class="active" to="/Color" exact>色彩使用</router-link>
				<li>组件</li>
			</ul>
		</ul>
		<!-- <button @click="showRouter">para</button> -->
	</div>
</template>

<script>
export default{
	data:function(){
		return{
			id: this.$route.params.id,
		}
	},
	created:function(){
		window.addEventListener('scroll', function(){
			let mainList = document.getElementsByClassName('mainList')[0];
			// console.log(pageYOffset + 'px');
			if (pageYOffset>80 && !mainList.classList.contains("fixedMainList")) {
				mainList.classList.add("fixedMainList");
			} else if(pageYOffset <= 80 && mainList.classList.contains("fixedMainList")) {
				mainList.classList.remove("fixedMainList");
			}
		})
	},
	methods:{
		// showRouter:function() {
		// 	console.log(this.$route.params);
		// }
	}
}
</script>

<style scoped>
@import url("../style/style.css");
</style>
