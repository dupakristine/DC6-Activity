<template>
  <div>
    <!-- Use Vue Meta for dynamic page titles -->
    <Head>
      <title>{{ pageTitle }}</title>
    </Head>

    <!-- Use a responsive navigation component -->
    <Navbar :user="user" />

    <AppLayout>
      <template #header>
        <!-- Display the user's name -->
        <h2 class="font-semibold text-2xl text-gray-800 leading-tight">
          Welcome, {{ user.name }}
        </h2>
      </template>

      <!-- Dashboard Overview -->
      <div class="p-4 ">
        <!-- Client Count Card -->
        <div class="w-64 h-50 bg-white p-6 rounded-lg shadow-md ">
          <h3 class="text-lg font-semibold mb-4">Client Count</h3>
          <div class="flex items-center">
            <div class="text-4xl font-semibold text-gray-800">{{ clientCount }}</div>
            <div class="ml-2 text-gray-600">clients</div>
          </div>
        </div>
      </div>
    </AppLayout>
  </div>
</template>




<script>
export default {
  data() {
    return {
      // Dynamic page title
      pageTitle: 'Dashboard',

      // User data (replace with actual user data)
      user: {
        name: 'Kristine!',
        // Add more user details as needed
      },

      // Client count (replace with actual data)
      clientCount: 30,

      // Recent activity data (replace with actual data)
      recentActivity: [
        { id: 1, description: 'User A updated their profile.' },
        { id: 2, description: 'New support ticket created by User B.' },
        // Add more activity items here
      ],
    };
  },
};
</script>


  <script setup>
  import AppLayout from '@/Layouts/AppLayout.vue';
  import { Head, Link } from '@inertiajs/vue3';

  const prop = defineProps({
      clientCount: Number
  })
  </script>
