<script>
	import { Header } from '$lib/components/header';
	import { Sidebar } from '$lib/components/sidebar';
</script>

<main class="">
	<Header />

	<!-- <div class="container mx-auto px-12 py-6 h-screen"> -->
	<div class="w-screen h-screen flex">
		<div class="w-80">
			<Sidebar />
		</div>
		<slot />
	</div>
</main>
