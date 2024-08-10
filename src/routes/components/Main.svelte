<script>
    import { onMount } from 'svelte';
    import Step from './Step.svelte';
    import Header from './Header.svelte';

    let y = 0;
    let steps = [
        { name: 'Mobile App', icon: 'fa-solid fa-mobile', href: "https://github.com/RoronoaZX/ROTC-Mobile-App" },
        { name: 'Portfolio', icon: 'fas fa-briefcase', href: "https://nils-web-portfolio.vercel.app/" },
        { name: 'Web App', icon: 'fas fa-globe', href: "https://nilweb.vercel.app/" },
    ];

    const handleScroll = () => {
        y = window.scrollY;
    };

    onMount(() => {
        window.addEventListener('scroll', handleScroll);
        return () => {
            window.removeEventListener('scroll', handleScroll);
        };
    });

    let benefits = [
        {
            name: 'Creative Thinker',
            description: 'I bring a unique perspective to every project, thriving on innovation and originality...'
        },
        {
            name: 'Analytical Thinker',
            description: 'I’m developing my skills in breaking down complex projects into manageable tasks...'
        },
        {
            name: 'Collaborative',
            description: 'I’m learning to effectively engage with others, valuing diverse perspectives...'
        }
    ];
</script>

<main class="flex flex-col flex-1 p-4">
    <Header {y} />

    <!-- Introduction Section -->
    <section id="introPage" class="grid grid-cols-1 lg:grid-cols-1 gap-10 py-8 sm:py-14">
        <div class="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10">
            <div class="flex justify-center lg:justify-start items-center">
                <img src="images/profile2.jpg" alt="Profile Image" class="w-32 h-32 lg:w-48 lg:h-48 rounded-full object-cover" />
            </div>
            <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
                Hi! I'm <span>Nil</span> Lim <br /> Full Stack
                <span class="poppins text-violet-400">Developer</span>
            </h2>
            <p class="text-base sm:text-lg md:text-xl"> 
                I am a <span class="text-[#42b883]">Vue</span>.js developer specializing in the 
                <span class="text-[#00B4FF]">Quasar</span> framework, creating dynamic and responsive web applications with a robust 
                <span class="text-[#eb4432]">Laravel</span> backend but this portfolio is developed using <span class="text-[hsl(12,91%,62%)]">Svelte</span> and <span class="text-[#38bdf8]">Tailwind</span> CSS, showcasing my eagerness to explore and master new technologies.
            </p>
            <a class="blueShadow mx-auto lg:mr-auto lg:ml-0 text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-6 py-3 group rounded-full bg-white text-slate-950 cursor-pointer" href="#" target="_blank">
                <div class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"></div>
                <h4 class="relative z-9">Get in touch &rarr;</h4>
            </a>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="py-20 lg:py-32 flex flex-col gap-24">
        <div class="flex flex-col gap-2 text-center">
            <h6 class="text-lg sm:text-xl md:text-2xl">A few of my creative endeavors.</h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">Curious to <span class="poppins text-violet-400">see</span> my work?</h3>
        </div>
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
            {#each steps as step (step.name)}
                <Step {step}>
                    <p>
                        <span class="text-violet-400">{step.name}</span> Developed using <span class="text-[#42b883]">Vue</span>.js with the <span class="text-[#00B4FF]">Quasar</span> framework and <span class="text-[#119EFF]">Capacitor</span>, this app provides a comprehensive digital manual tailored for ROTC, ensuring easy access to essential information on the go.
                    </p>
                </Step>
            {/each}
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-20 pt-10 lg:pt-16 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative">
        <div class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4">
            <h6 class="text-lg sm:text-xl md:text-2xl">Want to know more?</h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">A bit <span class="poppins text-violet-400">about</span> me.</h3>
        </div>
        <p class="mx-auto poppins font-semibold text-lg sm:text-xl md:text-2xl">I am . . .</p>
        <div class="flex flex-col gap-20 w-full mx-auto max-w-[800px]">
            {#each benefits as benefit, index}
                <div class="flex gap-6 sm:gap-8">
                    <p class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold">0{index + 1}</p>
                    <div class="flex flex-col gap-6 sm:gap-8">
                        <h3 class="text-2xl sm:text-3xl md:text-5xl">{benefit.name}</h3>
                        <p>{benefit.description}</p>
                    </div>
                </div>
            {/each}
        </div>
        <h5 class="text-2xl sm:text-3xl font-semibold text-center poppins">The <span class="text-violet-400">Complete</span> Package</h5>
        <div class="flex flex-col overflow-x-scroll gap-10 max-w-[800px] mx-auto w-full">
            <table class="bg-white text-slate-700 rounded text-center">
                <thead class="border-b border-solid border-slate-200">
                    <tr>
                        <th />
                        <th class="whitespace-nowrap p-2 px-4">Dedication</th>
                        <th class="whitespace-nowrap p-2 px-4">Critical Thought</th>
                        <th class="whitespace-nowrap p-2 px-4">Interpersonal Skills</th>
                        <th class="whitespace-nowrap p-2 px-4">Programming Ability</th>
                    </tr>
                </thead>
                <tbody>
                    <tr class="border-b border-solid border-slate-200">
                        <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm">Candidate #1</td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                    <tr class="border-b border-solid border-slate-200">
                        <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm">Candidate #2</td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                    <tr>
                        <td class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm">Candidate #3</td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                </tbody>
            </table>
        </div>
    </section>
</main>

<style>
 
</style>
