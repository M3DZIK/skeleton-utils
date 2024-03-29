<script lang="ts">
    import { Icon } from '@steeze-ui/svelte-icon';
    import { Visibility, VisibilityOff } from "@steeze-ui/material-design-icons";

    import { ActionableInput, ActionableInputIcon } from "$lib";
    import { onMount } from 'svelte';

    export let value: string;
    export let width: string = 'w-full';

    let ref: HTMLInputElement;
    let visibility = false;

    onMount(() => {
        ref.type = 'password';
    });

    function toogleVisibility() {
        visibility = !visibility

        ref.type = visibility ? 'text' : 'password';
    }
</script>

<ActionableInput iconCount={1} bind:value bind:ref width={width}>
    <ActionableInputIcon>
        <button on:click={toogleVisibility}>
            {#if visibility}
                <Icon src={VisibilityOff} />
            {:else}
                <Icon src={Visibility} />
            {/if}
        </button>
    </ActionableInputIcon>
</ActionableInput>
