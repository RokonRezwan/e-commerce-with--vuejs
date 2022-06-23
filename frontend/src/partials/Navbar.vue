<template>
    <div>
        <nav class="navbar navbar-expand-lg fixed-top navbar-light bg-light container">
            <div class="container-fluid px-2">
                <a class="navbar-brand" href="/">
                    <img src="../assets/logo.png" alt="logo" width="40" height="30"> Vue Vite
                </a>

                <a class="btn btn-outline-danger position-relative d-sm-block d-md-block d-lg-none ms-auto"
                    id="dropdownMenuClickableOutside" data-bs-toggle="offcanvas" data-bs-auto-close="outside"
                    href="#offcanvasExample" aria-expanded="false">
                    <i class="fa-solid fa-cart-shopping"></i>
                    <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger">
                        {{ cartCount }}
                    </span>
                </a>

                <button class="navbar-toggler ms-2" type="button" data-bs-toggle="collapse"
                    data-bs-target="#navbarTogglerDemo02" aria-controls="navbarTogglerDemo02" aria-expanded="false"
                    aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>

                <div class="collapse navbar-collapse" id="navbarTogglerDemo02">

                    <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                        <li class="nav-item">
                            <router-link to="/" class="nav-link border-end border-gray" active-class="active">Home
                            </router-link>
                        </li>
                        <li class="nav-item">
                            <router-link to="/products" class="nav-link border-end border-gray" active-class="active">
                                Products</router-link>
                        </li>
                        <li class="nav-item">
                            <router-link to="/cart" class="nav-link border-end border-gray" active-class="active">Cart
                            </router-link>
                        </li>
                        <li class="nav-item">
                            <router-link to="/checkout" class="nav-link border-end border-gray" active-class="active">
                                Checkout
                            </router-link>
                        </li>
                        <li class="nav-item">
                            <router-link to="/about" class="nav-link border-end border-gray" active-class="active">About
                            </router-link>
                        </li>
                        <li class="nav-item">
                            <router-link to="/contact" class="nav-link" active-class="active">Contact</router-link>
                        </li>
                    </ul>
                    <div class="btn-group d-none d-lg-block">
                        <a class="btn btn-outline-danger position-relative" id="dropdownMenuClickableOutside"
                            data-bs-toggle="offcanvas" data-bs-auto-close="outside" href="#offcanvasExample"
                            aria-expanded="false">
                            <i class="fa-solid fa-cart-shopping"></i>
                            <span
                                class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger">
                                {{ cartCount }}
                            </span>
                        </a>
                    </div>

                </div>
            </div>
        </nav>


        <div class="offcanvas offcanvas-end" tabindex="-1" id="offcanvasExample"
            aria-labelledby="offcanvasExampleLabel">
            <div class="offcanvas-header">
                <h5 class="offcanvas-title" id="offcanvasExampleLabel">Cart Item ( {{ cartCount }} )</h5>
                <button type="button" class="btn-close text-reset" data-bs-dismiss="offcanvas"
                    aria-label="Close"></button>
            </div>
            <div class="offcanvas-body">
                <NavbarCart />
            </div>
        </div>

    </div>
</template>

<script>
import NavbarCart from '../components/NavbarCart.vue';

export default {
    name: 'Navbar',
    components: {
        NavbarCart
    },

    computed: {
        cartCount() {
            return this.$store.getters.storeCart.length;
        }
    }
};

</script>

<style>
.active {
    background-color: #86cc8a;
    border-radius: 5px 5px 0 0;
}
</style>

