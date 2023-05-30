<template>
  <Disclosure as="nav" class="bg-white shadow" v-slot="{ open }">
    <div class="mx-auto max-w-7xl px-4 sm:px-6">
      <div class="flex h-16 justify-between">

        <!-- Logo and links -->
        <div class="flex gap-x-5">
          <div class="flex flex-shrink-0 items-center">
            <TextLogo class="h-5" />
          </div>
          <div class="hidden sm:ml-6 sm:flex sm:space-x-8">
            <Link v-for="item in navigation" :href="item.href"  class="inline-flex items-center border-b-2 border-transparent px-1 pt-1 text-sm font-medium text-gray-500 hover:border-gray-300 hover:text-gray-700">
              {{ item.name}}
            </Link>
          </div>
        </div>

        <!-- Right side (desktop) -->
        <div class="hidden sm:ml-6 sm:flex sm:items-center">

          <div class="flex gap-x-3">
            <Link :href="route('register')" type="button" class="rounded-md bg-slate-200 px-2.5 py-1.5 text-sm font-semibold text-slate-700 shadow-sm hover:bg-slate-300">Register</Link>

            <Link :href="route('login')"  class="rounded-md bg-lime-500 px-2.5 py-1.5 text-sm font-semibold text-white shadow-sm hover:bg-lime-600">Login</Link>
          </div>
        </div>

        <!-- Burger -->
        <div class="-mr-2 flex items-center sm:hidden">
          <!-- Mobile menu button -->
          <DisclosureButton class="inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-100 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500">
            <span class="sr-only">Open main menu</span>
            <Bars3Icon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
            <XMarkIcon v-else class="block h-6 w-6" aria-hidden="true" />
          </DisclosureButton>
        </div>
      </div>
    </div>

    <!-- Mobile menu -->
    <DisclosurePanel class="sm:hidden">
      <div class="space-y-1 pb-3 pt-2">
        <DisclosureButton v-for="item in navigation" :key="item.name" as="a" :href="item.href" :class="[item.current ? 'bg-gray-100 text-gray-900' : 'text-gray-900 hover:bg-gray-50 hover:text-gray-900', 'block rounded-md py-2 px-3 text-base font-medium']" :aria-current="item.current ? 'page' : undefined">{{ item.name }}</DisclosureButton>

      </div>
      <div class="border-t border-gray-200 space-y-1 pb-3 pt-4">
        <DisclosureButton as="a" :href="route('register')" class="text-gray-900 hover:bg-gray-50 hover:text-gray-900 block rounded-md py-2 px-3 text-base font-medium">Regsiter</DisclosureButton>
        <DisclosureButton as="a" :href="route('login')" class="text-gray-900 hover:bg-gray-50 hover:text-gray-900 block rounded-md py-2 px-3 text-base font-medium">Login</DisclosureButton>
      </div>
    </DisclosurePanel>

  </Disclosure>
</template>

<script setup>
import { Disclosure, DisclosureButton, DisclosurePanel, Menu, MenuButton, MenuItem, MenuItems } from '@headlessui/vue'
import { Bars3Icon, BellIcon, XMarkIcon } from '@heroicons/vue/24/outline'
import TextLogo from "@/Components/logos/TextLogo.vue"

let navigation = [
    { name: 'Overview', href: "#", current: route().current('overview') },
    { name: 'Features', href: "#", current: route().current('features') },
    { name: 'Pricing', href: "#", current: route().current('pricing') },

]

</script>