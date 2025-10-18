<template>
	<div class="card-container">
		<h1 class="name">Dainty CADET</h1>
		<h2 class="subtitle">Développeur Indépendant<br />Carte de visite</h2>
		<a class="subtitle bland" href="/Dainty_Cadet.vcf" download="Dainty_Cadet.vcf">📇 Contacts</a>

		<div class="qrs">
			<div class="qr-block" v-for="(link, index) in links" :key="index">
				<a :href="link.url" target="_blank" rel="noopener noreferrer">
					<img :src="link.qr" :alt="link.label" class="qr-img" />
				</a>
				<p>{{ link.label }}</p>
			</div>
		</div>
	</div>
</template>

<script setup>
const links = [
{
    label: "LinkedIn",
    url: "https://www.linkedin.com/in/dainty-c-12033415a/",
    qr: "/img/linkedin.png",
},
{
    label: "Curriculum Vitae",
    url: "https://scanned.page/p/Zs19H8",
    qr: "/img/CV.png",
},
{
    label: "GitHub : AggelosQubit",
    url: "https://github.com/AggelosQubit",
    qr: "/img/github.png",
},
];
</script>

<style >
body {
	margin: 0px;
}
.card-container {
	min-height: 100vh;
	background: linear-gradient(135deg, #041350, #ffffff, #e71010);
	color: #706f6f;
	text-align: center;
	font-family: 'Orbitron', sans-serif;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
}
.bland{
	color: #706f6f;
	text-decoration: none;
}

.name {
	font-size: 7rem;
	margin-bottom: 1rem;
}
.name:hover {
	transform: scale(1.05);
}
.subtitle {
	font-size: 1.3rem;
	margin-bottom: 4rem;
	opacity: 0.8;
}
.subtitle:hover {
	transform: scale(1.07);
}
.qrs {
	display: flex;
	gap: 8rem;
	flex-wrap: wrap;
	justify-content: center;
}

.qr-block {
	text-align: center;
}

.qr-img {
	width: 300px;
	height: 300px;
	border-radius: 12px;
	transition: transform 0.2s;
}

.qr-img:hover {
	transform: scale(1.05);
}

p {
	margin-top: 0.8rem;
	font-size: 1rem;
}
</style>
