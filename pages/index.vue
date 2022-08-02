<template>

    <div class="space-x-4 flex justify-center">
        <label for="appt">Start time :</label>

        <input type="time" id="appt" name="appt" min="09:00" max="18:00" required>
    </div>
    <div class="space-x-4 flex justify-center ">
        <label for="appt">End time :</label>

        <input type="time" id="appt" name="appt" min="09:00" max="18:00" required>
    </div>
    <div class=" flex mt-4 flex justify-center">
        <nav>
            <NuxtLink v-slot="{ navigate }" to="/form" custom>
                <button @click="navigate" class="bg-green-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
                    Book slot
                </button>
            </NuxtLink>
        </nav>
        <slot />
    </div>

</template>
