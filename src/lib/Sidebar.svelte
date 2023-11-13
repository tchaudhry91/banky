<script lang="ts">
	let tagInputChip = '';
	let tagInputChipList: String[] = [];

	import { Autocomplete, InputChip } from '@skeletonlabs/skeleton';
	import type { AutocompleteOption } from '@skeletonlabs/skeleton';

	const tagOptions: AutocompleteOption<string>[] = [
		{ label: 'history', value: 'history' },
		{ label: 'geography', value: 'geography' },
		{ label: 'sports', value: 'sports' },
		{ label: 'math', value: 'math' },
		{ label: 'science', value: 'science' },
		{ label: 'harrypotter', value: 'harrypotter' }
	];
	function onTagInputChipSelect(event: CustomEvent<AutocompleteOption<string>>): void {
		tagInputChipList.push(event.detail.label);
		tagInputChipList = tagInputChipList;
	}
</script>

<div class="w-96">
	<InputChip
		class="max-w-sm"
		bind:input={tagInputChip}
		bind:value={tagInputChipList}
		name="tags"
		placeholder="Filter Tags..."
	/>
	<div class="mt-5 card w-full max-w-sm max-h-48 p-4 overflow-y-auto" tabindex="-1">
		<Autocomplete
			bind:input={tagInputChip}
			options={tagOptions}
			denylist={tagInputChipList}
			on:selection={onTagInputChipSelect}
		/>
	</div>
</div>
