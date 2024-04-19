<script setup lang="ts">
  import sanity from '../services/client'
  import imageUrlBuilder from "@sanity/image-url";

  const imageBuilder = imageUrlBuilder(sanity);

  const query = `*[_type == "sujet"] {
  sujet,
  zedel,
  datum,
  vortrab,
  major,
  spiel,
  bild
  }[0...10]`;

  const sujets = await sanity.fetch(query);

  function imageUrlFor(source) {
      return imageBuilder.image(source);
  }
</script>

<template>
  <div class="sujets">
    <h1>Sujets</h1>
    <ul class="timeline timeline-snap-icon max-md:timeline-compact timeline-vertical">
      <li v-for="sujet in sujets" :key="sujet._id">
        <div class="timeline-middle">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="h-5 w-5"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z" clip-rule="evenodd" /></svg>
        </div>
        <div class="timeline-start md:text-end mb-10">
          <time class="font-mono italic">{{ sujet.datum }}</time>
          <div class="text-lg font-black">{{ sujet.sujet }}</div>
          {{ sujet.zedel }}
          <br />
          <table>
            <tr>
              <th>Vortrab</th>
              <td>{{ sujet.vortrab }}</td>
            </tr>
            <tr>
              <th>Major</th>
              <td>{{ sujet.major }}</td>
            </tr>
            <tr>
              <th>Spiel</th>
              <td>{{ sujet.spiel }}</td>
            </tr>
          </table>
          <img :src="imageUrlFor(sujet.bild).ignoreImageParams().width(240)" alt="Avatar Tailwind CSS Component" />
        </div>
        <hr/>
      </li>
      <li>
        <hr />
        <div class="timeline-middle">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="h-5 w-5"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.857-9.809a.75.75 0 00-1.214-.882l-3.483 4.79-1.88-1.88a.75.75 0 10-1.06 1.061l2.5 2.5a.75.75 0 001.137-.089l4-5.5z" clip-rule="evenodd" /></svg>
        </div>
        <div class="timeline-end mb-10">
          <time class="font-mono italic">1998</time>
          <div class="text-lg font-black">iMac</div>
          {{ sujets.zedel }}
        </div>
        <hr />
      </li>
    </ul>
  </div>
</template>

<style>
</style>
