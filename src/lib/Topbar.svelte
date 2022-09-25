<script lang="ts">
  import { onMount } from "svelte";
  import Marquee from "svelte-fast-marquee";

  let timezones = [
    {
      country: "Europe",
      city: "Zurich",
      time: "",
      flag: "🇪🇺",
    },
    {
      country: "America",
      city: "Los_Angeles",
      time: "",
      flag: "🇺🇸",
    },
    {
      country: "America",
      city: "Mexico_City",
      time: "",
      flag: "🇲🇽",
    },
    {
      country: "America",
      city: "Sao_Paulo",
      time: "",
      flag: "🇧🇷",
    },
    {
      country: "Asia",
      city: "Tokyo",
      time: "",
      flag: "🇯🇵",
    },
    {
      country: "Australia",
      city: "Sydney",
      time: "",
      flag: "🇦🇺",
    },
    {
      country: "America",
      city: "New_York",
      time: "",
      flag: "🇺🇸",
    },
    {
      country: "Asia",
      city: "Seoul",
      time: "",
      flag: "🇰🇷",
    },
    {
      country: "Africa",
      city: "Johannesburg",
      time: "",
      flag: "🇿🇦",  
    },
    {
      country: "America/Argentina",
      city: "Buenos_Aires",
      time: "",
      flag: "🇦🇷",
    },
  ];
  let promise = updateTime();
  async function getTime(country, city) {
    const API_STRING =
      "http://worldtimeapi.org/api/timezone/" + country + "/" + city;
    const response = await fetch(API_STRING);
    const data = await response.json();
    const time = data.datetime;
    return time.split("T")[1].split(".")[0];
  }
  
  async function updateTime() {
    let x: any;
    for (x in timezones) {
      timezones[x].time = await getTime(
        timezones[x].country,
        timezones[x].city
      );
    }
  }

  function handleOnMount() {
    promise = updateTime();
    setInterval(updateTime, 1000);
  }

  onMount(async () => {
    handleOnMount();
  });
</script>

<nav class="top-0 z-100 fixed w-full py-5 px-10">
  {#await promise}
    <h4 class="font-bold">...LOADING</h4>
  {:then}
    <h4 class="font-bold timezones">
      {#if screen.width > 768}
      <Marquee pauseOnHover={true} speed={120}>
        {#each timezones as timezone}
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{timezone.flag}
          {timezone.city}
          {timezone.time}
        {/each}
      </Marquee>
      {:else}
      <Marquee pauseOnHover={true} speed={60}>
        {#each timezones as timezone}
          &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{timezone.flag}
          {timezone.city}
          {timezone.time}
        {/each}
      </Marquee>
      {/if}
    </h4>
  {:catch error}
    <p style="color: red">{error.message}</p>
  {/await}
</nav>

<style>
  .timezones{
    font-size: 12px;
    margin:0!important;
  }
</style>