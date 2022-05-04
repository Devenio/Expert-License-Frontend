<template>
  <div class="w-full h-full flex">
    <div
      class="h-full w-full lg:w-1/2 bg-[url('/bg2.svg')] sm:flex items-center justify-center"
    >
      <div
        class="px-8 py-10 sm:rounded-md h-full sm:h-auto shadow-lg bg-[#171b31] text-[#FEFEFF] flex flex-col sm:block justify-center sm:min-w-[500px] lg:mx-7"
      >
        <div class="text-3xl font-bold flex items-center space-x-3">
          <div class="grow h-[1px] bg-[#fefeff] bg-opacity-10"></div>
          <div>Log In</div>
          <div class="grow h-[1px] bg-[#fefeff] bg-opacity-10"></div>
        </div>

        <div class="mt-10">
          <div
            class="flex items-center border-b-2 border-opacity-40 border-[#FEFEFF] space-x-2 pb-2"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="w-5 h-5 opacity-75"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              strokeWidth="2"
            >
              <path
                strokeLinecap="round"
                strokeLinejoin="round"
                d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"
              />
            </svg>

            <input
              type="text"
              class="grow bg-transparent outline-none focus-within:border-[#6901FF]"
              placeholder="Username..."
            />
          </div>

          <div
            class="flex items-center border-b-2 border-opacity-40 border-[#FEFEFF] space-x-2 pb-2 mt-7"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="w-5 h-5 opacity-50"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              stroke-width="2"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z"
              />
            </svg>

            <input
              :type="isOff ? 'password' : 'text'"
              class="grow bg-transparent outline-none focus-within:border-[#6901FF]"
              placeholder="Password..."
            />
            <!-- Eye off -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 cursor-pointer"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              stroke-width="2"
              @click="isOff = false"
              v-if="isOff"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M13.875 18.825A10.05 10.05 0 0112 19c-4.478 0-8.268-2.943-9.543-7a9.97 9.97 0 011.563-3.029m5.858.908a3 3 0 114.243 4.243M9.878 9.878l4.242 4.242M9.88 9.88l-3.29-3.29m7.532 7.532l3.29 3.29M3 3l3.59 3.59m0 0A9.953 9.953 0 0112 5c4.478 0 8.268 2.943 9.543 7a10.025 10.025 0 01-4.132 5.411m0 0L21 21"
              />
            </svg>
            <!-- Eye on -->
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6 cursor-pointer"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              stroke-width="2"
              @click="isOff = true"
              v-if="!isOff"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"
              />
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z"
              />
            </svg>
          </div>

          <button
            type="submit"
            class="mt-10 p-2 rounded-full w-full bg-gradient-to-r from-[#6901FF] to-[#6901FF] hover:shadow-[#6901FF40] hover:shadow-lg transition-all"
            @click="login"
          >
            <div class="lds-facebook" v-if="loading">
              <div></div>
              <div></div>
              <div></div>
            </div>

            <span v-else>Login</span>
          </button>
        </div>
      </div>
    </div>

    <img
      src="/Envy Avenue_.jfif"
      class="h-full w-0 lg:w-1/2 object-cover shadow-md [filter:brightness(0.4)]"
    />
  </div>
</template>

<script setup>
import { ref } from "vue";

const isOff = ref(true);
const loading = ref(false);

async function login() {
  loading.value = true;

  setTimeout(() => loading.value = false, 1000);
}
</script>
