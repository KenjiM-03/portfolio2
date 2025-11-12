
<script>

import Step from "./Step.svelte";
import {onMount} from "svelte";
let steps = [
    {
        name: "KulisApp",
        icon: "fa-solid fa-bug",
        href: "https://github.com/KenjiM-03?tab=repositories",
        description:
            "Smoljames Store is a a merchanising store created with Next.js, Commerce.js & Stripe! Commerce.js is a CMS for managing project and Stripe is used for all transaction handling.",
    },
    {
        name: "Grand Eagle Inventory System",
        icon: "fa-solid fa-warehouse",
        href: "https://github.com/KenjiM-03?tab=repositories",
        description:
            "Test for model robustness with customized test profiles and receive exhaustive reporting on the performance and potential vulnerabilities of your model.",
    },
    {
        name: "Prince Educational Supply Inventory System",
        icon: "fa-solid fa-book",
        href: "https://github.com/KenjiM-03?tab=repositories",
        description:
            "Augment your datasets with our filters and dataset manipulations to ensure your models are trained on the highest quality datasets (coming soon).",
    },
];
let benefits = [
    {
        metric: "10x",
        name: "a self taught developer",
        description:
            "I taught myself to code using free online resources and absolutely fell in love with the creativity and problem solving that is involved in developing and engineering innovative new online experiences. Starting of with JavaScript, HTML & CSS and evolving my knowledge base to include JavaScript frameworks, backend programming, design, cloud services and much much more.",
    },
    {
        name: "a product design & UX finatic",
        description:
            "Carefully crafting and designing amazing user experiences allows me to express and experiment with every morsel of creativity I have. I love the challenge of learning new design concepts and enabling users with amazing online experiences.",
    },
    {
        name: "an excellent communicator",
        description:
            "Communication is key and it's a paramount value of mine. I believe in transparency and constructive communication above all else. This helps me develop deep relationships and ensures my effectiveness and productivity in any work space with any team.",
    },
];
const texts = ["Developer", "Photographer", "Creative","Networking Savant"];
let displayText = "";
let index = 0;
let charIndex = 0;
const speed = 70;
const waitTime = 1500;
const cursor = "_";

onMount(() => {
    function type() {
        if (charIndex < texts[index].length) {
            displayText = `${texts[index].substring(0, charIndex + 1)}${cursor}`;
            charIndex++;
            setTimeout(type, speed);
        } else {
            setTimeout(erase, waitTime);
        }
    }

    function erase() {
        if (charIndex > 0) {
            displayText = `${texts[index].substring(0, charIndex - 1)}${cursor}`;
            charIndex--;
            setTimeout(erase, speed / 2);
        } else {
            index = (index + 1) % texts.length;
            setTimeout(type, speed);
        }
    }

    type();
});
</script>
<main>
    <section id = "intropage" class="grid grid-cols-1 lg:grid-cols-2 gap-10 md:gap-12 lg:gap-16 py-12 sm:py-16 lg:py-24 justify-center min-h-screen">
        <div class ="flex flex-col lg:justify-center text-center lg:text-left gap-6 md:gap-8 lg:gap-10">
            <h2 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
                My name is <span class="poppins text-[#FFEBD1]">Kenji</span> Mende<br/> A <span class="poppins text-[#FFEBD1]">
            {displayText}
            </span>
            </h2>
            <p class="text-base sm:text-lg md:text-xl leading-relaxed">
                A versatile <span class="poppins text-[#FFFDA7]">application developer</span> with a strong foundation in
                <span class="poppins text-[#FFFDA7]">network engineering</span> experienced in configuring and maintaining
                secure, efficient networks as well as developing modern, responsive web applications.
            </p>
<!--            <a class="blueShadow mx-auto lg:mr-auto text-base sm:text-lg md:text-xl poppins relative overflow-hidden px-5 py-2 group rounded-full bg-white text-slate-950 cursor-pointer" -->
<!--               href="#"-->
<!--               target="_blank"-->
<!--               >-->
<!--                <div class="absolute top-0 right-full w-full h-full1 bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"></div>-->
<!--                <h4 class="relative z-[10]">Contact me &rarr;</h4>-->
<!--            </a>-->
        </div>
        <div class="relative shadow-2xl grid place-items-center w-fit mx-auto overflow-hidden">


            <img
                    src="images/profile.jpg"
                    alt="pfp"
                    class="object-cover z-[2] max-h-[60vh] lg:max-h-[70vh] shadow-lg"
            />
        </div>

    </section>



    <section class="min-h-screen py-12 sm:py-16 lg:py-24 mt-12 lg:mt-0 flex flex-col justify-center gap-20 lg:gap-24" id="projects">
        <div class="flex flex-col gap-2 text-center">
            <h6 class="text-large sm:txt-xl md:text-2xl">A small peek on</h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
                Some of my  <span class="poppins text-[#FFEBD1]">Best Projects</span>

            </h3>

        </div>
        <a
                href="https://github.com/KenjiM-03"
                target="_blank"
                class="mx-auto px-4 py-2 rounded-md border border-solid border-white flex items-center gap-2 -mb-4 sm:-mb-0 -mt-10 hover:border-violet-700 duration-200"
        >
            <i class="fa-brands fa-github"/>
            <p>Visit my Github</p>
        </a>
        <div class="grid grid-cols-1 lg:grid-cols-3 gap-12 lg:gap-10">
            <Step step={steps[0]}>
                <p>
                    KulisApp is an insect identification application with geospatial mapping of insect sightings built on <strong
                        class="text-violet-400"
                >Flutter, YOLOv11, Geopandas, and PostgeSQL.</strong
                >
                    The app leverages machine learning and image recognition to accurately classify insect species in real time through photo uploads.
                    Its integrated mapping system allows users to visualize insect sightings on an interactive map, enabling spatial analysis of species distribution and density.

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
                    An inventory system built on the <strong class="text-violet-400"
                >T3 Stack</strong>
                   A web application, hosted on
                    <strong class="text-violet-400">vercel</strong>, that
                    consumes and caches the
                    <strong class="text-violet-400">Pokémon API</strong>
                    to display all Pokémon information. Gotta catch them all!
                </p>
            </Step>
        </div>
    </section>
    <section
            id="about"
            class="py-20 pt-10 lg:pt-16 lg:py-32 flex flex-col gap-16 sm:gap-20 md:gap-24 relative justify-center"
    >
        <div
                class="flex flex-col gap-2 text-center relative before:absolute before:top-0 before:left-0 before:w-2/3 before:h-1.5 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:w-2/3 after:h-1.5 after:bg-violet-700 py-4"
        >
            <h6 class="text-large sm:text-xl md:text-2xl">
                Want to know more?
            </h6>
            <h3 class="font-semibold text-3xl sm:text-4xl md:text-5xl">
                A bit <span class="poppins text-violet-400">about</span> me.
            </h3>
        </div>
        <p class="mx-auto poppins fast font-semibold text-lg sm:text-xl md:text-2xl">My name</p>
        <div class="flex flex-col gap-20 w-full mx-auto max-x-[800px]">
            {#each benefits as benefit, index}
                <div class="flex gap-6 sm:gap-8">
                    <p class="poppins text-4xl sm:text-5xl md:text-6xl text-slate-500 font-semibold">
                        0{index+1}
                    </p>
                    <div class="flex flex-col gap-6 sm:gap-8">
                        <h3 class="text-2xl sm:text-3xl md:text-5xl">
                            {benefit.name}

                        </h3>
                        <p>{benefit.description}</p>
                    </div>
                </div>
            {/each}
            <div
                    class="flex flex-col overflow-x-scroll gap-10 max-w-[800px] mx-auto w-full"
            >
                <table class="bg-white text-slate-700 rounded text-center">
                    <thead class={"border-b border-solid border-slate-200  "}>
                    <tr class="">
                        <th />
                        <th class="whitespace-nowrap p-2 px-4">Candidate #1</th>
                        <th class="whitespace-nowrap p-2 px-4">Candidate #2</th>
                        <th class="whitespace-nowrap p-2 px-4">Candidate #3</th>
                        <th
                                class="bg-violet-700 text-white whitespace-nowrap p-4 px-8"
                        >Me</th
                        >
                    </tr>
                    </thead>
                    <tbody>
                    <tr class="border-b border-solid border-slate-200">
                        <td
                                class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm"
                        >Dedication</td
                        >
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                    <tr class="border-b border-solid border-slate-200">
                        <td
                                class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm"
                        >Critical Thought</td
                        >
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                    <tr>
                        <td
                                class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm"
                        >Interpersonal Skills</td
                        >
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                    <tr class="border-t border-solid border-slate-200">
                        <td
                                class="border-r border-solid border-white pl-4 pr-8 py-4 font-semibold text-sm"
                        >Progamming Ability</td
                        >
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-xmark text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-slate-500" /></td>
                        <td><i class="fa-solid fa-check text-green-500" /></td>
                    </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </section>
</main>
