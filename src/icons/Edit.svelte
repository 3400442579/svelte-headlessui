<script lang="ts">
	interface Props {
		active: boolean
		[key: string]: any
	}

	let { ...props }: Props = $props()
</script>

<svg
	class={props.class}
	aria-hidden="true"
	viewBox="0 0 20 20"
	fill="none"
	xmlns="http://www.w3.org/2000/svg"
	><path
		d="M4 13V16H7L16 7L13 4L4 13Z"
		stroke-width="2"
		fill={props.active ? '#8B5CF6' : '#EDE9FE'}
		stroke={props.active ? '#C4B5FD' : '#A78BFA'}
	/></svg
>
