<script lang="ts">
	import { AppShell } from '@skeletonlabs/skeleton';

	import Sidebar from '$lib/sidebar.svelte';
</script>

<AppShell>
	<!-- (header) -->
	<svelte:fragment slot="sidebarLeft"><Sidebar /></svelte:fragment>
	<!-- (sidebarRight) -->
	<!-- (pageHeader) -->
	<!-- Router Slot -->
	<div class="container">
		<slot />
	</div>
	<!-- ---- / ---- -->
	<!-- (pageFooter) -->
	<!-- (footer) -->
</AppShell>

