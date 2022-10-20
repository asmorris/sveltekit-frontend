<script>
  import { queryStore, gql, getContextClient } from '@urql/svelte';

  const testField = queryStore({
    client: getContextClient(),
    query: gql`
      query {
        testField
      }
    `,
  });
</script>

{#if $testField.fetching}
  <p>Loading...</p>
{:else if $testField.error}
  <p>Oh no... {$testField.error.message}</p>
{:else}
  <p>{$testField.data.testField}</p>
{/if}

