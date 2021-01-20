<template>
  <div>
    <h2>Available gatsbys</h2>
    <ul>
      <li v-for="gatsby in gatsbys" v-bind:key="gatsby.id" >
		  <gatsby v-bind:value="gatsby"  />
	  </li>
    </ul>
  </div>
</template>

<script>
import gatsby from './gatsby.vue';
export default {
  components: { gatsby },
  data() {
    return {
      gatsbys: [
        {
		  id : 1,
		  name: "Half by Joe",
		  subs : 0,
		  parts : 4
        },
        {
			id: 2,
		  name: "Half by Anna",
		  subs: 0,
		  parts : 4
        },
        {
		  id : 3,
		  name: "Full by Joe",
		  subs: 0,
		  parts : 4,
		  
        },
      ],
    };
  },
  methods : {
	  order : function(gatsby) {
		  gatsby.subs++;
	  }
  },
  computed : {
	  
  }
};
</script>

<style  scoped>

	ul {
		list-style : none;
	}

	li {
		margin: 1em;
		padding: 0.5em;
		border: 1px solid;
		border-radius: 0.25em;
	}
</style>