<script>
	import SearchFilter from '$lib/SearchFilter.svelte';
	import Field from '$lib/Field.svelte';
	import Markdown from '$lib/Markdown.svelte';
	import Portal from '$lib/Portal.svelte';
	// import BetterAccordion from '$lib/BetterAccordion.svelte';
	// import Toggle from '$lib/Toggle.svelte';
	let isToggled = false;

	let text = '';
	$: console.log(text);
	let search = '';
	let items = ['scott', 'wes', 'landon', 'courtney', 'lucie', 'brooklyn', 'Samson'];
</script>

<h1>Welcome to Level Up UI {search}</h1>

<Portal>
	<Markdown bind:text />
</Portal>

<Field bind:value={search} label="Search" insrustions="Type to search" placeholder="Joe" />

<Field value={0} label="Number" type="number" />

<SearchFilter {items} bind:search />

<!-- <BetterAccordion isOpen={false} buttonText="Do I need a credit card??">
	<div>
		<p>
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Impedit iure a accusamus harum hic,
			ullam obcaecati dicta ab praesentium qui cupiditate labore recusandae mollitia ad, fugiat
			neque possimus! Aperiam, distinctio!
		</p>
	</div>
</BetterAccordion> -->

<!-- <Toggle bind:isToggled label="Beta" />
<Toggle bind:isToggled label="Beta" style="--toggleBackgroundColor: red;" /> -->

{#if isToggled}
	<h1>I'm toggled</h1>
{/if}
