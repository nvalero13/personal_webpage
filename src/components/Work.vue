<template>
	<div class="flex flex-col items-center mb-24">
		<div
			class="text-light text-2xl items-center border-b-2 border-light pb-2 pt-10"
		>
			<h2 class="font-extralight">Projects</h2>
		</div>

		<div
			class="grid sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-10 mt-10 mx-10"
		>
			<article
				v-for="project in projects"
				class="w-[300px] cursor-pointer hover:scale-105 transition-all border-light border-2"
			>
				<img
					class="h-48 w-full object-cover object-left border-light"
					:src="project.img"
					:alt="`${project.title} Image`"
				/>
				<div
					class="border-light border-t-4 p-5 h-64 flex flex-col justify-between text-light"
				>
					<div>
						<h3 class="text-xl font-light my-1">{{ project.title }}</h3>
						<p class="font-extralight">{{ project.desc }}</p>
					</div>

					<div>
						<p class="text-main">{{ project.tags }}</p>

						<div class="mt-2 flex gap-2">
							<a
								v-if="project.github !== undefined"
								:href="project.github"
								target="_blank"
								class="text-main border-main border px-2 py-1 hover:bg-main hover:text-white"
								><i class="fa-brands fa-github"></i> Source Code
							</a>
							<a
								v-if="project.deploy !== undefined"
								:href="project.deploy"
								target="_blank"
								class="text-main border-main border px-2 py-1 hover:bg-main hover:text-white"
								><i class="fa-solid fa-rocket"></i> Deploy
							</a>
							<a
								v-if="project.behance !== undefined"
								:href="project.behance"
								target="_blank"
								class="text-main border-main border px-2 py-1 hover:bg-main hover:text-white"
								><i class="fa-brands fa-behance"></i> Behance
							</a>
						</div>
					</div>
				</div>
			</article>
		</div>
	</div>
</template>

<script setup>
import { ref } from 'vue';
import PaperBagImg from '../assets/paper-bag.png';
import TuduImg from '../assets/tudu.png';
import MetImg from '../assets/met.png';
import PenjapenjollsImg from '../assets/penjapenjolls.png';
import MetroRecipesImg from '../assets/metro-recipes.png';

const projects = ref([
	{
		img: PaperBagImg,
		title: 'Paper Bag',
		desc: 'A paper bag raffle maker with funny animations.',
		github: 'https://github.com/nvalero13/paper-bag',
		deploy: 'https://nvalero13.github.io/paper-bag/',
		tags: 'HTML, CSS & Javascript',
	},
	{
		img: TuduImg,
		title: 'Tudú',
		desc: 'Task manager that allows the creation of tasks, subtasks, categories and filters by date.',
		github: 'https://github.com/nvalero13/ironhack-final-project',
		deploy: 'https://nvalero-tudu.netlify.app/',
		tags: 'Vue, Supabase, Tailwind',
	},
	{
		img: PenjapenjollsImg,
		title: 'Penjapenjolls',
		desc: 'E-commerce of contemporary jewelry',
		deploy: 'https://penjapenjolls.com/',
		tags: 'Wordpress, Photography',
	},
	{
		img: MetImg,
		title: 'Met Museum Gallery',
		desc: 'Unconventional web gallery that consumes the MET museum API.',
		github: 'https://github.com/nvalero13/met-web',
		behance: 'https://www.behance.net/gallery/112703353/MET-Web-Design',
		tags: 'React, API',
	},
	{
		img: MetroRecipesImg,
		title: 'Metro Recipes',
		desc: 'Video game app catalog that uses the RAWG API',
		github: 'https://github.com/nvalero13/metro-recipes',
		tags: 'React Native, API',
	},
]);
</script>

<style scoped></style>
