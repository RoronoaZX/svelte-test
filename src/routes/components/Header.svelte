<script>
    export let y;
    
    $: showImage = y > 0
    let tabs = [
        {name: 'Projects', link:'#projects'},
        {name: 'About me', link:'#about'},
        // {name: 'Blog', '#blog'},
    ]
</script>

<header class={"sticky z-[10] top-0 duration-200 px-6 flex items-center justify-between border-solid " + (y > 0 ? ' py-4 bg-slate-950 border-violet-950' : ' py-6 bg-transparent border-transparent')}>

    <div class="flex items-center">
        {#if showImage}
            <img src="images/profile2.jpg" alt="Profile Image" class="w-8 h-8 rounded-full object-cover mr-2" />
        {/if}
        <h1 class="font-medium flex items-center">
            <b class="font-bold poppins  mr-1">Nil</b>  Lim
        </h1>
    </div>

   
    <div class="sm:flex items-center gap-4 hidden">
        {#each tabs as tab, index}
            <a class="duration-200 hover:text-violet-400" href={tab.link}>
                <p>{tab.name}</p>
            </a>
        {/each}
   
    <a class="blueShadow relative overflow-hidden px-5 py-2 group rounded-full bg-white text-slate-950" href="#" target="_blank">
        <div class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200">

        </div>
        <h4 class="relative z-9">Get in touch</h4>
    </a>
</div>
</header>