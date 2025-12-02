<template>
	<div class="card-container">
		<h1 class="name">Kairos AggelosQubit Lab </h1>

		<h3 class="subtitle">Dainty CADET</h3>
		<h3 class="subtitle">Développeur Indépendant<br/>Carte de visite</h3>
		

		<div class="qrs">
			<div class="qr-block" v-for="(link, index) in links" :key="index">
				<a :href="link.url" target="_blank" rel="noopener noreferrer">
					<img :src="link.qr" :alt="link.label" class="qr-img" />
				</a>
				<p>{{ link.label }}</p>
			</div>
		</div>

		<a class="subtitle bland" href="/contact/Dainty_Cadet.vcf" download="Dainty_Cadet.vcf">📇 Contact Channels</a>
		
		<div>
			<!-- Bouton pour ouvrir la modale -->
			<button id="openLegal" class="mentions" @click="toggleModal()">
				Mentions légales
			</button>

			<!-- Modale -->
			<div id="legalModal" class="legalModalClass" :class="{ visible: isOpen }">
				<div class="card" >
					<div>
						<h2 style="text-align:center; color:#ff6;">Mentions légales</h2>
						<p><b>Nom commercial :</b> Kairos AggelosQubit Lab</p>
						<p><b>Nom :</b> Dainty CADET</p>
						<p><b>Statut :</b> Entrepreneur individuel – Micro-entreprise</p>
						<p><b>SIREN :</b> 899 742 241</p>
						<p><b>Adresse :</b> 11 Rue Henri Rol-Tanguy, 77500 Chelles, France</p>
						<p><b>Courriel :</b> aggelosQubit@gmail.com</p>
						<p><b>Hébergeur :</b> Netlify</p>
						<p><b>Activités principale (Soon principale):</b> Développement web, création numérique et conception d’outils logiciels.</p>
						<p><b>Activités complémentaires #1:</b> Vente à distance – Exploitation de boutique E-commerce, vente de produits non réglementés sur internet</p>
						<p><b>Propriété intellectuelle :</b> L’ensemble du contenu (textes, visuels, design) de Kairos AggelosQubit Lab est protégé par le Code de la propriété intellectuelle.</p>
						<p><b>Données personnelles :</b> Aucune donnée personnelle n’est collectée directement sur ce site.</p>
						<p><b>Responsabilité :</b> L’éditeur ne saurait être tenu responsable du contenu des sites externes accessibles via les QR codes.</p>
						<div style="text-align:center; margin-top:1rem;">
							<button id="closeLegal" class="closeLegalClass" @click="toggleModal()">
								Fermer
							</button>
						</div>
					</div>

				</div>
			</div>
		</div>
	</div>
	
</template>

<script setup>
import { ref } from 'vue'

const isOpen = ref(false);


function toggleModal() {
	console.log("IN toggleModal")
	isOpen.value = !isOpen.value;
}
	const links = [
		{label: "LinkedIn",url: "https://www.linkedin.com/in/dainty-c-12033415a/",qr: "/img/linkedin.png",},
		{label: "Curriculum Vitae",url: "/Dainty_CADET_CV_FR.pdf",qr: "/img/aggelosQubit.webp",},
		{label: "GitHub : AggelosQubit",url: "https://github.com/AggelosQubit",qr: "/img/github.png",},
	];

</script>

<style >
body {
	margin: 0px;
}
.card{
	display: flex;
	background: #262a38;
	color :rgb(255, 255, 255);
	margin: 5%;
	padding: 5%;
	font-size: 1rem;
	width: 100%;
}
.mentions{
	color: #ffffff;
	justify-items: center;
	background:none; 
	border:none; 
	cursor:pointer;
}

.closeLegalClass{
	background:#ff6; 
	border:none; 
	padding:0.5rem 1rem; 
	border-radius:8px; 
	cursor:pointer;
}
.legalModalClass{
	display:none;	
	position:fixed;	
	top:0; 
	left:0; 
	width:100%; 
	height:100%;	
	background:rgba(0,0,0,0.7);	
	backdrop-filter:blur(4px);	
	z-index:9999;	
	text-align: left;
}
.legalModalClass.visible {
  display: flex; /* Le display change ici */
}
.subDivLegalModalClass{
	background:#121212;
	color:#eee;
	border-radius:12px;
	max-width:700px;
	padding:2rem;
	overflow-y:auto;
	max-height:85vh;
	box-shadow:0 0 25px rgba(0,0,0,0.4);
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
	margin-top: 70px;
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
	margin-top: 1.5rem;
	margin-bottom: 1.5rem;
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
