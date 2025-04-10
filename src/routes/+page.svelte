<script>
	import { Button } from '$lib/components/ui/button';
	import classes from '../button.module.css';
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

<Button class={classes['button-main']}>Hey there</Button>

<Button>I am original</Button>
