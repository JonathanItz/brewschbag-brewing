<script setup lang="ts">
import { ParticlesBg } from "@/components/ui/particles-bg";
import { onMounted, ref, Transition } from "vue";

const showContent = ref(false)

onMounted(() => {
	setTimeout(() => {
		showContent.value = true
	}, 1000);
})
</script>

<template>
	<div
		class="relative flex min-h-screen w-full flex-col items-center justify-center overflow-hidden rounded-lg border bg-background md:shadow-xl">

		<Transition name="fade">
			<div class="relative z-100 transition-all" v-if="showContent">
				<img src="/logo.png" alt="Brewshbag Brewing logo" class="size-40 mx-auto">
				<span
					class="whitespace-pre-wrap bg-gradient-to-b from-emerald-400 to-white/10 bg-clip-text text-8xl font-semibold leading-30 text-transparent">
					Brewschbag Brewing
				</span>
			</div>
		</Transition>
		<ParticlesBg class="absolute inset-0" :quantity="200" :ease="100" color="#fff" :staticity="10" refresh />
	</div>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
	transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
	opacity: 0;
}
</style>