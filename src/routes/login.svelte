<script>
import { isLogin } from '../store';
import { goto } from "$app/navigation";
import { onMount } from "svelte";
let loginValue;

isLogin.subscribe(value => {
		loginValue = value;
});

onMount(() => {
    if (loginValue) {
    console.log("redirecting to Home page");
    goto("/");
    };
});

function login() {
    isLogin.set(!loginValue);
    if (loginValue) {
    goto("/");
    };
};
</script>

<div class="mx-auto md:h-screen flex flex-col justify-center items-center px-6 pt-8 pt:mt-0">
    <a href="/" class="text-2xl font-semibold flex justify-center items-center mb-8 lg:mb-10">
        <img src="logo.png" class="h-13 mr-4" alt="SMUCT Logo">
    </a>
    <!-- Card -->
    <div class="bg-white shadow rounded-lg md:mt-0 w-full sm:max-w-screen-sm xl:p-0">
        <div class="p-6 sm:p-8 lg:p-16 space-y-8">
            <h2 class="text-2xl lg:text-3xl font-bold text-gray-900">
                Login
            </h2>
            <form class="mt-8 space-y-6" action="#">
                <div>
                    <label for="username" class="text-sm font-medium text-gray-900 block mb-2">Your Username</label>
                    <input type="username" name="username" id="username" class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-cyan-600 focus:border-cyan-600 block w-full p-2.5" placeholder="201077007" required>
                </div>
                <div>
                    <label for="password" class="text-sm font-medium text-gray-900 block mb-2">Your password</label>
                    <input type="password" name="password" id="password" placeholder="••••••••" class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-cyan-600 focus:border-cyan-600 block w-full p-2.5" required>
                </div>
                <div class="flex items-start">
                    <div class="flex items-center h-5">
                        <p class="text-sm text-teal-500 hover:underline ml-auto">Lost Password? Contact with your Department</p>
                    </div>
                </div>
                <button on:click|preventDefault={login} type="submit" class="text-white bg-cyan-600 hover:bg-cyan-700 focus:ring-4 focus:ring-cyan-200 font-medium rounded-lg text-base px-5 py-3 w-full sm:w-auto text-center">Login to your account</button>
            </form>
        </div>
    </div>
</div>
