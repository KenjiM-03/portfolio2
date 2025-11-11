
<script>

import Step from "./Step.svelte";
let steps = [
    {
        name: "KulisApp",
        icon: "fa-solid fa-bug",
        description:
            "Smoljames Store is a a merchanising store created with Next.js, Commerce.js & Stripe! Commerce.js is a CMS for managing project and Stripe is used for all transaction handling.",
    },
    {
        name: "Grand Eagle Inventory System",
        icon: "fa-solid fa-warehouse",
        description:
            "Test for model robustness with customized test profiles and receive exhaustive reporting on the performance and potential vulnerabilities of your model.",
    },
    {
        name: "Prince Educational Supply Inventory System",
        icon: "fa-solid fa-book",
        description:
            "Augment your datasets with our filters and dataset manipulations to ensure your models are trained on the highest quality datasets (coming soon).",
    },
];
</script>
<main>
    <section id = "intropage" class="grid grid-cols-1 lg:grid-cols-2 gap-10 md:gap-12 lg:gap-16 py-12 sm:py-16 lg:py-24 justify-center min-h-screen">
        <div class ="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10">
            <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
                My name <span class="poppins text-[#FFEBD1]">Jeff</span> Bezos<br/> Absolute <span class="poppins text-[#FFEBD1]">
            Developer
            </span>
            </h2>
            <p class="text-base sm:text-lg md:text-xl">
                My name <span class="poppins text-[#FFFDA7]">Jeff</span> Bezos<br/> Absolute <span class="poppins text-[#FFFDA7]">
            Developer
            </span>
            </p>
            <a class="blueShadow mx-auto lg:mr-auto text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-5 py-2 group rounded-full bg-white text-slate-950 cursor-pointer" 
               href="#"
               target="_blank"
               >
                <div class="absolute top-0 right-full w-full h-full1 bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"></div>
                <h4 class="relative z-[10]">Contact me &rarr;</h4>
            </a>
        </div>
        <div class="relative shadow-2xl grid place-items-center w-fit mx-auto overflow-hidden">
            <img
                    src={"images/profile.jpg"}
                    alt="Zetane Engine"
                    class="object-cover z-[2] max-h-[60vh] lg:max-h-[70vh] shadow-lg"
            />
        </div>

    </section>



    <section class="min-h-screen py-12 sm:py-16 lg:py-24 mt-12 lg:mt-0 flex flex-col justify-center gap-20 lg:gap-24" id="projects">
        <div class="flex flex-col gap-2 text-center">
            <h6 class="text-large sm:txt-xl md:text-2xl">Some of my work</h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl"> My name <span class="poppins text-[#47945A]">Jeff</span> Bezos<br/> Absolute <span class="poppins text-[#D1FFDC]">
            Developer</span>

            </h3>

        </div>
        <a
                href="https://www.youtube.com/watch?v=dQw4w9WgXcQ"
                target="_blank"
                class="mx-auto px-4 py-2 rounded-md border border-solid border-white flex items-center gap-2 -mb-4 sm:-mb-0 -mt-10 hover:border-violet-700 duration-200"
        >
            <i class="fa-regular fa-circle-play"/>
            <p>Watch the video</p>
        </a>
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
            <Step step={steps[0]}>
                <p>
                    KulisApp is an insect identification application with geospatial mapping of insect sightings built on <strong
                        class="text-violet-400"
                >Flutter, YOLOv11, Stripe & Node.js + Express.js!</strong
                > Commerce.js is a product CMS and Stripe is used for all transaction
                    handling.
                </p>
            </Step>
            <Step step={steps[1]}>
                <p>
                    An inventory management application built with <strong
                        class="text-violet-400">Next.js</strong
                >,
                    <strong class="text-violet-400">Java</strong
                    >
                    & <strong class="text-violet-400">MYSQL</strong> CRUD application
                    that allows a user to login, manage a company's inventory system, as well as admins to manage employees.

                </p>
            </Step>
            <Step step={steps[2]}>
                <p>
                    An inventory <strong class="text-violet-400"
                >SvelteKit & TailwindCSS</strong
                >
                    web application, hosted on
                    <strong class="text-violet-400">Netlify</strong>, that
                    consumes and caches the
                    <strong class="text-violet-400">Pokémon API</strong>
                    to display all Pokémon information. Gotta catch them all!
                </p>
            </Step>
        </div>
    </section>
</main>
