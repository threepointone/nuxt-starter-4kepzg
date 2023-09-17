<script setup lang="ts">
import PartySocket from 'partysocket';

const addParty = () => {
  const ws = new PartySocket({
    host: 'project.name.partykit.dev', // or localhost:1999 in dev
    room: 'my-room',
    // add an optional id to identify the client,
    // if not provided, a random id will be generated
    // note that the id needs to be unique per connection,
    // not per user, so e.g. multiple devices or tabs need a different id
    id: 'some-connection-id',

    // optionally, specify the party to connect to.
    // if not provided, will connect to the "main" party defined in partykit.json
    party: 'main',
  });

  console.log(ws);
};

onMounted(() => {
  addParty();
});
</script>

<template>
  <div class="h-screen flex items-center justify-center">
    <div class="text-center p-12">Check error in console</div>
  </div>
</template>
