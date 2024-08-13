<template>
<header>
    <div class="logo-container">
        <img
        src="@/assets/Logo.png"
        alt="Ascendia Elevator Services Logo"
        class="logo"
        />
        <h1>Ascendia Elevator Services</h1>
    </div>
    <nav>
        <ul>
        <li>
            <router-link to="/" exact-active-class="active-link"
            >Home</router-link
            >
        </li>
        <li>
            <router-link to="/about" active-class="active-link"
            >About Us</router-link
            >
        </li>
        <li>
            <router-link to="/services" active-class="active-link"
            >Services</router-link
            >
        </li>
        <li>
            <router-link to="/clients" active-class="active-link"
            >Clients & Testimonials</router-link
            >
        </li>
        <li>
            <router-link to="/contact" active-class="active-link"
            >Contact</router-link
            >
        </li>
    </ul>
    </nav>
    </header>
</template>

<script>
export default {
    name: "SiteHeader",
};
</script>

<style scoped>
/* Estilos para el encabezado */
header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: #f0fcfe; /* Azul Claro */
    padding: 1rem 2rem;
}

.logo-container {
    display: flex;
    align-items: center;
}

.logo {
    height: 100px;
    margin-right: 1rem;
}

nav ul {
    list-style: none;
    display: flex;
    gap: 2.5rem;
    margin: 0;
    padding: 0;
}

nav ul li {
    position: relative;
}

nav ul li .active-link {
    color: #0c3756; /* Azul Profundo */
    font-weight: bold;
}

nav a {
    color: #333333; /* Gris Oscuro */
    text-decoration: none;
    padding: 0.5rem 1rem;
    border-radius: 25px;
    transition: background-color 0.3s;
}

nav a:hover {
  background-color: #b7d9e2; /* Azul Pastel */
}

.active-link {
  background-color: #86b6c6; /* Azul Suave */
}
</style>
