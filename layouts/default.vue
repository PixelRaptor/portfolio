<template>
	<div class="layout" id="body">
		<TopBar />
		<Hero />
		<ul class="router-tabs">
			<li class="link">
				<nuxt-link to="/#works">Works</nuxt-link>
			</li>
			<li class="link">
				<nuxt-link to="/about#me">About me</nuxt-link>
			</li>
		</ul>
		<div class="line"></div>
		<Nuxt />
		<PageFooter />
		<!-- <ProjectPopup class="" v-if="$store.state.showProject" /> -->
	</div>
</template>

<script lang="ts">
import Vue from "vue";
import TopBar from "~/components/TopBar.vue";
import PageFooter from "~/components/complex/PageFooter.vue";
import ProjectPopup from "~/components/complex/ProjectPopup.vue";

export default Vue.extend({
	name: "LayoutPage",
	components: { TopBar, PageFooter, ProjectPopup },
	// mounted() {
	// 	this.$nextTick(() => {
	// 		this.$nuxt.$loading.start();
	// 		setTimeout(() => this.$nuxt.$loading.finish(), 2000);
	// 	});
	// },
});
</script>

<style lang="scss" scoped>
.layout {
	padding: var(--side-padding);
	.router-tabs {
		display: flex;
		justify-content: space-between;
		max-width: 11rem;
		list-style: none;
		margin: 4rem 0px 1rem;

		.link {
			text-align: left;
			a {
				text-decoration: none;
				&.nuxt-link-active {
					text-decoration: underline;
					text-underline-offset: 1rem;
				}
			}
		}
	}
}

@media only screen and (min-width: 672px) {
	.layout {
		.router-tabs {
			margin: 3rem 0px 1rem;
			.link {
				a {
					&.nuxt-link-active {
					}
				}
			}
		}
	}
}
@media only screen and (min-width: 932px) {
	.layout {
		margin: auto;
		max-width: 900px;
	}
}
@media only screen and (min-width: 1232px) {
	.layout {
		max-width: 1200px;
	}
}
</style>
