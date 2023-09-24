<template>
  <div>
    <Head title="Clients" />
    <AppLayout>
      <template #header>
        <!-- Improved header with background and text -->
        <div class=" py-6 text-black">
          <h2 class="font-semibold text-3xl text-center">Client List</h2>
        </div>
      </template>

      <!-- Client Cards Section -->
      <div class="py-8 max-w-7xl mx-auto sm:px-6 lg:px-8">
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-6">
          <!-- Client Cards -->
          <ClientCard
            v-for="client in clientsList"
            :key="client.id"
            :client="client"
          />
        </div>
      </div>

        <!-- Paginator Section -->
      <div class="flex justify-center items-center my-4">
        <Pagination
          :links="clients.links"
          :currentPage="clients.current_page"
          :totalPages="clients.total"
          pageRange="4"
        />
      </div>
    </AppLayout>
  </div>
</template>


<script setup>
import AppLayout from '@/Layouts/AppLayout.vue';
import ClientCard from '@/Components/ClientCard.vue';
import Pagination from '@/Components/Pagination.vue';
import { Head } from '@inertiajs/vue3';

const props = defineProps({
  clients: Object,
});

const clientsList = props.clients.data;
</script>