<script>
	import { gsap } from "gsap"
	import { onMount } from "svelte"

	onMount(() => {
		gsap.from(".card", { opacity: 0, y: 200, scale: 0, ease: "power1.out", duration: 1})
		gsap.from(".card__top", { y: 150, delay: .5, ease: "power3.easeIn", duration: .8 })
		gsap.from(".card__pic", { scale: 0, delay: 1, ease: "bounce.out", duration: 1 })
		gsap.from(".card__user", { opacity: 0, y: 50, delay: 1, ease: "power1.out", duration: 1 })
		gsap.from(".card__location", { opacity: 0, y: 70, delay: 1.2, ease: "power1.out", duration: 1 })
		
		const stats = document.querySelectorAll(".card__stat")

		stats.forEach((stat, i) => {
			gsap.from(`.${stat.classList[1]}`, { opacity: 0, y: 50, delay: (i+2) / 3, ease: "power1.out", duration: .8 })
		})
	})
</script>

<main class="card">
	<div class="card__top"></div>
	<div class="card__bottom">
		<div class="card__profile">
			<img src="/images/image-victor.jpg" alt="Victor Crest Profile Pic" class="card__pic">
			<div class="card__user">
				<h1 class="card__user-name">Victor Crest</h1>
				<p class="card__user-age">26</p>
			</div>
			<p class="card__location">London</p>
		</div>
		<div class="card__stats">
			<div class="card__stat card__stat--1">
				<h2 class="card__stat-subheadline">80K</h2>
				<p class="card__stat-label">Followers</p>
			</div>
			<div class="card__stat card__stat--2">
				<h2 class="card__stat-subheadline">803K</h2>
				<p class="card__stat-label">Likes</p>
			</div>
			<div class="card__stat card__stat--3">
				<h2 class="card__stat-subheadline">1.4K</h2>
				<p class="card__stat-label">Photos</p>
			</div>
		</div>
	</div>
</main>

<a href="https://www.frontendmentor.io/profile/Remus432" target="_blank" class="profile">
	<img class="profile__pic" src="/images/Remus.jpg" alt="Remus Buhaianu - Frontend Developer" />
</a>

<style lang="scss">
	.card {
		box-shadow: 0 5rem 10rem -2rem rgba(#08465E, .5);
		width: 32rem;

		&__top {
			background-image: url("/images/bg-pattern-card.svg");
			background-size: cover;
			background-repeat: no-repeat;
			border-top-left-radius: 1.5rem;
			border-top-right-radius: 1.5rem;
			padding-top: 14rem;
			position: relative;
			z-index: -1;
		}

		&__bottom {
			background-color: #fff;
			border-bottom-left-radius: 1.5rem;
			border-bottom-right-radius: 1.5rem;
		}

		&__profile {
			align-items: center;
			display: flex;
			flex-direction: column;
			margin-bottom: -2rem;
			transform: translateY(-5rem);
		}

		&__user {
			align-items: center;
			display: flex;
			margin-top: 2.4rem;
		}

		&__user-name {
			font-size: 1.8rem;
			margin-right: .8rem;
		}

		&__location {
			color: #6B7082;
			font-size: 1.4rem;
			margin-top: .8rem;
		}

		&__pic {
			border: 5px solid #fff;
			border-radius: 50%;
		}

		&__stats {
			border-top: 1px solid #E8E9EC;
			display: flex;
			justify-content: space-between;
			padding: 2.4rem 4.1rem;
		}

		&__stat {
			text-align: center;
		}

		&__stat-subheadline {
			font-size: 1.8rem;
		}

		&__stat-label {
			color: #6B7082;
			font-size: 1rem;
			margin-top: .9rem;
		}

		@media screen and (min-width: 768px) {
			& {
				width: 35rem;
			}
		}
	}

	.profile {
		bottom: 2.5vh;
		position: fixed;
		right: 5vw;

		&::before {
			background-color: #fff;
			border-top-left-radius: 2rem;
			border-bottom-left-radius: 2rem;
			content: "Coded by me";
			color: #F16A16;
			position: absolute;
			padding: 1rem;
			display: inline-block;
			right: 5vw;
			top: 45%;
			transform: translateY(-50%);
			width: 250%;
			z-index: -1;
		}

		&__pic {
			border: 3px solid #fff;
			border-radius: 50%;
			width: 6rem;
		}

		@media screen and (min-width: 768px) {
			& {
				right: 2.5vw;

				&::before {
					max-width: 170%;
				}

				&__pic {
					border: 5px solid #fff;
					width: 10rem;
				}
			}
		}
	}
</style>