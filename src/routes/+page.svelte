<script context="module">
	// Import any necessary modules or data here
	// For example, import the icons for care tips and related products
	import { careTips, relatedProducts } from '$lib/utils/data'; // Assuming you have a separate data file
</script>

<script lang="ts">
	// Add any TypeScript types or logic here
</script>

<template>
	<div class="grid grid-cols-1 gap-8 py-12 md:py-24 lg:grid-cols-[1fr_300px] lg:py-32">
		<!-- First section -->
		<div class="relative overflow-hidden rounded-lg">
			<img
				src="/placeholder.svg"
				alt="Colorful Reptile"
				width="1200"
				height="800"
				class="aspect-[3/2] w-full object-cover"
			/>
			<div class="absolute inset-0 bg-gradient-to-t from-gray-900/75 to-transparent"></div>
			<div
				class="absolute inset-0 flex flex-col items-center justify-center p-6 text-center text-white"
			>
				<h1 class="text-3xl font-bold tracking-tighter sm:text-5xl">
					Discover the Wonders of Reptile Morphs
				</h1>
				<p class="mt-4 max-w-[600px] text-lg leading-relaxed">
					Explore our collection of rare and stunning reptile morphs, perfect for any reptile
					enthusiast.
				</p>
			</div>
		</div>

		<!-- Second section -->
		<div class="space-y-6">
			<!-- Reptile Care Tips -->
			<div class="rounded-lg border bg-card text-card-foreground shadow-sm" data-v0-t="card">
				<div class="flex flex-col space-y-1.5 p-6">
					<h3 class="whitespace-nowrap text-2xl font-semibold leading-none tracking-tight">
						Reptile Care Tips
					</h3>
				</div>
				<div class="p-6">
					<ul class="space-y-2 text-sm">
						<!-- List items -->
						{#each careTips as tip}
							<li>
								<a class="flex items-center gap-2 font-medium hover:underline" href={tip.link}>
									<svg class="h-5 w-5 text-gray-500" viewBox={tip.icon.viewBox}>
										{#each tip.icon.paths as path}
											<path d={path}></path>
										{/each}
									</svg>
									{tip.title}
								</a>
							</li>
						{/each}
					</ul>
				</div>
			</div>

			<!-- Related Products -->
			<div class="rounded-lg border bg-card text-card-foreground shadow-sm" data-v0-t="card">
				<div class="flex flex-col space-y-1.5 p-6">
					<h3 class="whitespace-nowrap text-2xl font-semibold leading-none tracking-tight">
						Related Products
					</h3>
				</div>
				<div class="p-6">
					<ul class="space-y-2 text-sm">
						<!-- List items -->
						{#each relatedProducts as product}
							<li>
								<a class="flex items-center gap-2 font-medium hover:underline" href={product.link}>
									<svg class="h-5 w-5 text-gray-500" viewBox={product.icon.viewBox}>
										{#each product.icon.paths as path}
											<path d={path}></path>
										{/each}
									</svg>
									{product.title}
								</a>
							</li>
						{/each}
					</ul>
				</div>
			</div>
		</div>
	</div>

	<!-- Other sections -->
	<!-- Add other sections here -->
</template>
