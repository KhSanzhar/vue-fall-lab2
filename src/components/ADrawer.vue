<template>

  <div
      v-if="isOpen"
  >

    <div
        class="fixed inset-0 bg-black bg-opacity-50 z-40"
        @click="$emit('close')"
    >
    </div>

    <div
        class="fixed top-0 left-0 h-full bg-white shadow-lg z-50"
    >

      <div class="my-4 mx-5">
        <div class="w-80 border rounded-xl bg-teal-500 flex justify-center mb-5">
          <div class="text-2xl font-bold text-white">Menu</div>
        </div>

        <div class="w-80 border-none rounded-xl bg-white">
          <div class="py-2 flex flex-col gap-5 mb-16">
            <div
                v-for="genre in genres"
                :key="genre"
                class="border rounded-xl bg-teal-500 text-white flex justify-center cursor-pointer text-xl"
            >
              {{ genre }}
            </div>
          </div>

          <div
              class="border rounded-xl bg-teal-500"
          >
            <div>
              Contacts
            </div>

            <div
              v-for="(contact, label) in contacts"
              :key="label"
              class=""
            >
              {{label}}: {{contact}}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import useGenres from "@/composables/useGenres.js";
import useContacts from "@/composables/useContacts.js";

defineProps({
  isOpen: {
    type: Boolean,
  }
})

const genres = useGenres().map((g) => (g + ' blog').toUpperCase());

const contacts = useContacts();

</script>