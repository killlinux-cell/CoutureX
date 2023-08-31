<template>
<nav class="nav-conatiner">
        <div class="logo">
            <!-- Mettez votre logo ici -->
            <a href="#"> CoutureX</a>
        </div>
        <div class="nav-middle">
            <ul class="nav-links">
                <li><a href="#hero">ACCUEIL</a></li>
                <li><a href="#presentation">PRESENTATION</a></li>
                <li><a href="#collection">COLLECTIONS</a></li>
                <li><a href="#contact">CONTACT</a></li>
            </ul>
       </div>
        <div class="nav-right">
         <!-- <a href="" class=" btn-nav">FIND A TABLE</a> -->
        </div>
        <!-- hambuger menu -->
        <div class="hamburger-menu-container" @click="openMenu">
				<div
					class="hamburger-menu"
					:class="{ close: isActive }"
					id="toggle-menu"
				></div>
			</div>
        <!-- hambuger menu -->
        <!-- responsive mobile -->
        <div class="nav-mobile">
			<a href="#hero" class="mobile-element" @click="openMenu">Accueil</a>
			<a href="#presentation" class="mobile-element" @click="openMenu">Presentation</a>
			<a href="#collection" class="mobile-element" @click="openMenu">Collection</a> 
			<a href="#contact" class="mobile-element" @click="openMenu">Contact</a>
		</div>
        <!-- responsive mobile -->
    </nav>
</template>

<script>
export default {
	name: "Navbar",
    data() {
		return {
			isScrolled: false,
			isActive: false,
			isDropdownVisible: false,
		};
	},
	created() {
		window.addEventListener("scroll", this.onScroll);
	},
	destroyed() {
		window.removeEventListener("scroll", this.onScroll);
	},
	methods: {
		onScroll(event) {
			this.isScrolled = window.scrollY > 0;
		},

		openMenu(event) {
			const toggleButton = document.getElementsByClassName("hamburger-menu")[0];
			const navLinks = document.getElementsByClassName("nav-mobile")[0];

			if (this.isActive == false) {
				navLinks.style.transform = "translate(-100%, 0)";
				this.isActive = true;
			} else if (this.isActive == true) {
				navLinks.style.transform = "translate(100%, 0)";
				this.isActive = false;
			}
		},
		showDropdown() {
			this.isDropdownVisible = true;
		},
		hideDropdown() {
			this.isDropdownVisible = false;
		},
		triggerModal() {
			this.$emit("showModal");
		},
	},
};
</script>

<style scoped>
@import "../style.css";
</style>
