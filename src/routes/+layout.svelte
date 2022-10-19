<script>
  import { createClient, setContextClient } from '@urql/svelte'

  import "../app.css";

  const client = createClient({
    url: 'http://localhost:3000/graphql',
  })

  setContextClient(client)
</script>

<slot />
