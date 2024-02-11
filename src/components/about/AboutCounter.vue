<script>
import counter from 'vue3-autocounter';
export default {
	components: {
		counter,
	},
	data: () => {
		return  {
			counters: [
				{
					id: 1,
					title: "Lorem Ipsum",
					amount: 12,
				},
				{
					id: 2,
					title: "Lorem Ipsum",
					amount: 80,
					suffix: "%"
				},
				{
					id: 3,
					title: "Lorem Ipsum",
					amount: 45,
					prefix: "$",
					suffix: "K"
				},
				{
					id: 4,
					title: "Lorem Ipsum",
					amount: 560,
				},
			]}
	},
};
</script>

<template>
	<div class="mt-10 sm:mt-20 bg-primary-light dark:bg-ternary-dark shadow-sm">
		<!-- About me counters -->
		<div class="font-general-regular container mx-auto py-20 block sm:flex sm:justify-between sm:items-center">
			<div class="mb-20 sm:mb-0" v-for="counter in counters" :key="counter.id">
				<counter
					ref="counter"
					:startAmount="0"
					:endAmount=counter.amount
					:duration="1"
					:autoinit="true"
					:suffix=counter.suffix
					:prefix=counter.prefix 
					class="font-general-medium text-4xl font-bold text-secondary-dark dark:text-secondary-light mb-2"
					aria-label="About Status Counter"
				/>
				<span
					class="block text-md text-ternary-dark dark:text-ternary-light"
				>
					{{ counter.title }}
				</span>
			</div>
		</div>
	</div>
</template>
