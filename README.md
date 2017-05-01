# Twitter Bootstrap Tabs

I use this in Laravel applications.

There are many ways to include this into your app.

	Vue.component('tab', require('./Tab.vue'));
	Vue.component('tabs', require('./Tabs.vue'));

or:

	import Tab from './Tab.vue';
	Vue.component('tab', Tab);
	// etc

And use it:

	<tabs>
	  <tab name="Records" selected>

	  </tab>
	  <tab name="Settings">

	  </tab>
	  <tab name="Alerts">

	  </tab>
	</tabs>
