<script>
  export let name, bgImg;
</script>

<div class="p-3 w-[200px] h-[300px] rounded-xl overflow-hidden flex justify-center items-center cursor-pointer border-solid border-2 border-gray-600" 
  style={`background-image: url(${bgImg});
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat`}>
  <div class="w-fit bg-slate-800 bg-opacity-70 p-2 rounded-xl">        
    <p class="text-lg text-center text-white font-semibold">{name}</p>  
  </div>
</div>