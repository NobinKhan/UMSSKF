<script>
import { isLogin } from '../store';
import { goto } from "$app/navigation";
import { onMount } from "svelte";
import Navbar from '$lib/Navbar.svelte';
import Sidebar from '$lib/Sidebar.svelte';
import Footer from '$lib/Footer.svelte';
import '../app.css';

let loginValue;

isLogin.subscribe(value => {
		loginValue = value;
});

onMount(() => {
    if (!loginValue) {
    console.log("redirecting to login page");
    goto("/login");
    };
});

function logout() {
    isLogin.set(!loginValue);

    if (loginValue) {
    goto("/");
    };
};

</script>

{#if loginValue}
<Navbar/>
<div class="flex overflow-hidden bg-white pt-16">
    <Sidebar/>
    <div id="main-content" class="h-full w-full bg-gray-50 relative overflow-y-auto lg:ml-64">
        <main>
            <slot/>
        </main>
        <!-- <Footer/> -->
    </div>
</div>
{:else}
<slot/>
{/if}


