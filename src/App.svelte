<script>
  import Card from "./components/Card.svelte";
  
  let data = [
    {
      name: "Sakura Miko",
      key: "miko",
      bgImg: "https://media.tenor.com/p86jSzfI-KEAAAAC/sakura-miko.gif"
    },
    {
      name: "Minato Aqua",
      key: "aqua",
      bgImg: "https://media.tenor.com/SAg8wyuG9N4AAAAd/minato-aqua-minato.gif"
    },
    {
      name: "Tokoyami Towa",
      key: "towa",
      bgImg: "https://media.tenor.com/ztlNAqw_00EAAAAC/%E5%B8%B8%E9%97%87%E3%83%88%E3%83%AF-%E3%83%9B%E3%83%AD%E3%83%A9%E3%82%A4%E3%83%96.gif"
    }
  ];

  const handleCardClick = (name) => {
    const event = new CustomEvent("InterComponent", {
      detail: {
        customData: {
          from: "list-hololive",
          action: "click-card",
          additionalData: {
            name
          }
        },
      },
    });
    dispatchEvent(event);
  }
</script>

<style>
  * {
    font-family: 'Quicksand', sans-serif;
  }
</style>

<section class="w-full min-h-screen flex flex-col justify-center items-center gap-6 p-4">
<h1 class="text-5xl text-center font-semibold text-[#50e0ff]">TALENTS</h1>
<div class="w-full flex justify-center items-center gap-10">
  {#each data as {name, key, bgImg}}
  <div on:click={() => handleCardClick(key)}>
    <Card name={name} bgImg={bgImg} />
  </div>
  {/each}
</div>
</section>
