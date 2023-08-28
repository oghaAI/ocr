<script>
	import DropTarget from '@uppy/drop-target';
	import Uppy from '@uppy/core';
	import { onMount } from 'svelte';

	let stuff = '';
	onMount(() => {
		const uppy = new Uppy();
		uppy.use(DropTarget, {
			target: '#drag-drop'
		});
		uppy.on('file-added', (file) => {
			console.log(file.name);
			stuff = file.name;
		});
	});
</script>

<div>
	<div class="" id="drag-drop">
		<div class="py-3 px-3 border-r-2 h-screen overflow-y-scroll">
			<div>
				<ul role="list" class="divide-y divide-gray-100">
					<li class="flex gap-x-2 py-3">
						<div class="min-w-0 r">
							<p class="text-sm font-semibold leading-6 text-gray-900 line-clamp-1">
								{stuff}
							</p>
						</div>
					</li>
					<li class="flex gap-x-2 py-3">
						<div class="min-w-0 r">
							<p class="text-sm font-semibold leading-6 text-gray-900 line-clamp-1">
								SomeFileName.pdf
							</p>
						</div>
					</li>
				</ul>
			</div>
		</div>
	</div>
</div>
