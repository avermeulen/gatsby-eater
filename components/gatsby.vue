<template>
	<div>
		<div>
			{{value.status}} {{ value.name }} ({{status}})
		</div>
		<div>
			<button v-on:click="subscribe" v-if="!ordered" >Order</button>
			<span v-if="ordered">
				<strong>Your gatsby is on it's way</strong>
			</span>
		</div>
	</div>
</template>

<script>
export default {
	props : ["value"],
	data : function(){
		return {
			subs : 0,
		}
	},
	methods : {
		subscribe : function(){
			this.subs++;
		}
	},
	computed : {
		status : function(vm) {
			if (vm.subs < vm.value.parts) {
				return `${vm.subs} / ${vm.value.parts}`
			} else {
				return `Active`
			}
		},
		ordered : function(vm) {
			return vm.status === "Active"
		}
		
	}
}
</script>
