<script>
	import SearchFilter from '$lib/SearchFilter.svelte';
	import Field from '$lib/Field.svelte';
	import Markdown from '$lib/Markdown.svelte';
	import Modal from '$lib/Modal.svelte';
	import Toast from '$lib/toast/Toast.svelte';
	import { toast } from '$lib/toast/toast';
	import Portal from '$lib/Portal.svelte';
	// import BetterAccordion from '$lib/BetterAccordion.svelte';
	// import Toggle from '$lib/Toggle.svelte';
	let isToggled = false;
	let isModalOpen = false;
	let text = '';

	$: console.log(text);
	let search = '';
	let items = ['scott', 'wes', 'landon', 'courtney', 'lucie', 'brooklyn', 'Samson'];
</script>

<h1>Welcome to Level Up UI {search}</h1>

<Modal {isModalOpen}>
	<div style="background: white; box-shadow: 1px 1px 4px rgba(0,0,0,0.3);">
		<Field bind:value={search} label="Search" insrustions="Type to search" placeholder="Joe" />
		<Field value={0} label="Number" type="number" />
	</div>
</Modal>

<Toast duration={3000} />
<button on:click={() => toast.send('New Message' + Math.random())}>New Toast</button>

<!-- <button on:click={() => (isModalOpen = true)}>Open Modal Form</button> -->

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
