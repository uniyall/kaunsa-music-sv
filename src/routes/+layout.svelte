<script lang="ts">
	import '../app.css';
	import Calendar from '@lucide/svelte/icons/calendar';
	import House from '@lucide/svelte/icons/house';
	import Inbox from '@lucide/svelte/icons/inbox';
	import * as Sidebar from '$lib/components/ui/sidebar/index.js';
	import Appsidebar from '$lib/components/Appsidebar.svelte';
	let { children } = $props();
	const items = [
		{
			title: 'Home',
			url: '/',
			icon: House
		},
		{
			title: 'Login',
			url: '/login',
			icon: Inbox
		},
		{
			title: 'Random',
			url: '/random',
			icon: Calendar
		}
	];
</script>

<Sidebar.Provider>
	<Sidebar.Root collapsible="none" variant="inset" class="w-full">
		<Sidebar.Inset >
			<main>
				{@render children()}
			</main>
		</Sidebar.Inset>
		<Sidebar.Content>
			<Sidebar.Group />
			<Sidebar.GroupLabel>Menu</Sidebar.GroupLabel>
			<Sidebar.GroupContent>
				<Sidebar.Menu>
					{#each items as item (item.title)}
						<Sidebar.MenuItem>
							<Sidebar.MenuButton>
								{#snippet child({ props })}
									<a href={item.url} {...props}>
										<item.icon />
										<span>{item.title}</span>
									</a>
								{/snippet}
							</Sidebar.MenuButton>
						</Sidebar.MenuItem>
					{/each}
				</Sidebar.Menu>
			</Sidebar.GroupContent>
			<Sidebar.Group />
		</Sidebar.Content>
	</Sidebar.Root>
</Sidebar.Provider>
