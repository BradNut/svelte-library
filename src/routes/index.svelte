<script>
	import BetterAccordion from '$lib/BetterAccordion.svelte';
	import Toggle from '$lib/Toggle.svelte';
	let isToggled = false;
</script>

<h1>Welcome to Level Up UI</h1>

<BetterAccordion isOpen={false} buttonText="Do I need a credit card??">
	<div>
		<p>
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Impedit iure a accusamus harum hic,
			ullam obcaecati dicta ab praesentium qui cupiditate labore recusandae mollitia ad, fugiat
			neque possimus! Aperiam, distinctio!
		</p>
	</div>
</BetterAccordion>

<Toggle bind:isToggled label="Beta" />
<Toggle bind:isToggled label="Beta" style="--toggleBackgroundColor: red;" />

{#if isToggled}
	<h1>I'm toggled</h1>
{/if}
