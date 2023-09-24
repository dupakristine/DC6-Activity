<template>
    <div class="custom-card m-4 transition-transform transform hover:-translate-y-1 hover:shadow-lg">
      <div class="card-content p-4">
        <div class="icon text-center">
      <i class="fas fa-user text-4xl mb-2 text-black"></i>
    </div>

    <!-- Client Name -->
    <h5 class="card-title text-xl font-semibold text-gray-800">
      {{ clientFullName }}
    </h5>

    <!-- Client Details -->
    <div class="card-details mt-2">
      <p class="card-text text-gray-600">{{ client.address }}</p>
      <p class="card-text text-gray-600">{{ client.phone }}</p>
    </div>


        <div class="flex justify-end mt-4">
          <button
            type="button"
            class="px-4 py-1.5 rounded-md text-white text-sm"

            :class="{
              'bg-black': color == '',
              'bg-blue-600': color == 'Blue',
              'bg-red-600': color == 'Red',
              'bg-green-600': color == 'Green',
            }"
          >
            Click me
          </button>
        </div>
      </div>
    </div>
  </template>

  <script setup>
  import { defineProps } from 'vue';
  import { inject } from 'vue';
  const color = inject('color')

  const props = defineProps({
    client: Object,
  });
  </script>

  <style scoped>
  .custom-card {
    width: 350px;
    background-color: #F3F4F6;
    border: 1px solid #e2e8f0;
    border-radius: 0.5rem;
    margin: 0.5rem;
    cursor: pointer;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    transition: transform 0.2s, box-shadow 0.2s;
  }

  .custom-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }

  .card-content {
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .card-title {
    font-size: 1.25rem;
    font-weight: bold;
  }

  .icon {
    color: #222020;
  }

  .card-details {
    color: #352020;
  }

  .card-text {
    margin-bottom: 0.25rem;
  }

  .card-level {
    font-size: 0.75rem;
    padding: 0.25rem 0.5rem;
    border-radius: 0.25rem;
    align-self: flex-start;
  }
  </style>
