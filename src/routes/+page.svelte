<script>
    import { ActionableInput, PasswordInput } from '$lib';
    import ActionableInputIcon from '$lib/components/input/ActionableInputIcon.svelte';

    let value = '';
    let passwordValue = '';
</script>

<a href="/test" class="btn variant-ghost">test page</a>

<p>Actionable Input</p>

<ActionableInput width="w-[200px]" iconCount={2} bind:value on:keydown={console.log}>
    <ActionableInputIcon>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
            <path d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" />
        </svg>
    </ActionableInputIcon>

    <ActionableInputIcon>
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
            <path d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"/>
        </svg>
    </ActionableInputIcon>
</ActionableInput>

<p>Password Input</p>

<PasswordInput width="w-[200px]" bind:value={passwordValue} />

<span>{value}</span>
