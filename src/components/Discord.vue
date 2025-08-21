<script setup>
import '../styles/tailwind.css'
</script>

<template>
    <div class="flex h-screen antialiased text-neutral-300 bg-neutral-800">
        <!-- Server List -->
        <div class="flex flex-col items-center w-16 py-4 space-y-3 bg-neutral-900">
            <a href="#" class="relative block">
                <img alt="Discord" src="https://logodownload.org/wp-content/uploads/2017/11/discord-logo-4-1.png" class="w-12 h-12 mx-auto" />
            </a>
            <div class="w-8 h-px bg-neutral-700"></div>
            <a href="#" class="relative block p-2 bg-neutral-700 rounded-lg">
                <svg class="w-8 h-8" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path><circle cx="12" cy="7" r="4"></circle></svg>
            </a>
            <a href="#" class="relative block p-2 bg-neutral-800 rounded-full">
                <svg class="w-8 h-8 text-green-400" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 15H9v-2h2v2zm0-4H9V7h2v6z"/></svg>
            </a>
            <a href="#" class="relative flex items-center justify-center w-12 h-12 text-2xl text-green-400 bg-neutral-800 rounded-full">+</a>
        </div>

        <!-- Channel List -->
        <div class="flex flex-col w-64 bg-neutral-800">
            <div class="px-4 py-3 font-bold text-white shadow-md">Tailwind CSS</div>
            <div class="flex-1 p-2 space-y-2 overflow-y-auto">
                <p class="p-2 text-neutral-400">TEXT CHANNELS</p>
                <a href="#" class="block p-2 text-neutral-200 bg-neutral-700 rounded"># general</a>
                <a href="#" class="block p-2 text-neutral-400 hover:bg-neutral-700 rounded"># announcements</a>
                <a href="#" class="block p-2 text-neutral-400 hover:bg-neutral-700 rounded"># feedback</a>
                <p class="p-2 text-neutral-400">VOICE CHANNELS</p>
                <a href="#" class="block p-2 text-neutral-400 hover:bg-neutral-700 rounded">General</a>
                <a href="#" class="block p-2 text-neutral-400 hover:bg-neutral-700 rounded">Music</a>
            </div>
            <div class="flex items-center p-2 space-x-4 bg-neutral-900">
                <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Avatar" class="w-10 h-10 rounded-full">
                <div class="flex-1">
                    <div class="font-semibold text-white">John Doe</div>
                    <div class="text-xs text-neutral-400">#1234</div>
                </div>
            </div>
        </div>

        <!-- Main Chat Area -->
        <div class="flex flex-col flex-1 bg-neutral-700">
            <!-- Chat Header -->
            <div class="flex items-center justify-between px-4 py-3 text-white border-b border-neutral-800 shadow-md">
                <div class="flex items-center">
                    <span class="text-2xl text-neutral-500">#</span>
                    <span class="ml-2 font-semibold">general</span>
                </div>
            </div>

            <!-- Messages -->
            <div class="flex-1 p-4 space-y-4 overflow-y-auto">
                <!-- Message -->
                <div class="flex items-start space-x-4">
                    <img src="https://randomuser.me/api/portraits/women/34.jpg" alt="Avatar" class="w-10 h-10 rounded-full">
                    <div class="flex-1">
                        <div class="flex items-baseline space-x-2">
                            <span class="font-semibold text-white">Jane Doe</span>
                            <span class="text-xs text-neutral-400">Today at 10:00 AM</span>
                        </div>
                        <p class="text-neutral-300">Hey everyone! How's it going?</p>
                    </div>
                </div>
                <!-- Message -->
                <div class="flex items-start space-x-4">
                    <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Avatar" class="w-10 h-10 rounded-full">
                    <div class="flex-1">
                        <div class="flex items-baseline space-x-2">
                            <span class="font-semibold text-white">John Doe</span>
                            <span class="text-xs text-neutral-400">Today at 10:02 AM</span>
                        </div>
                        <p class="text-neutral-300">Doing great, Jane! Just working on this new Vue component.</p>
                    </div>
                </div>
            </div>

            <!-- Chat Input -->
            <div class="p-4 bg-neutral-700">
                <div class="relative">
                    <input type="text" placeholder="Message #general" class="w-full py-2 pl-10 pr-4 text-white bg-neutral-600 border border-neutral-800 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500">
                    <div class="absolute inset-y-0 left-0 flex items-center pl-3">
                        <svg class="w-6 h-6 text-neutral-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6"></path></svg>
                    </div>
                </div>
            </div>
        </div>

        <!-- User List -->
        <div class="flex flex-col w-64 bg-neutral-800">
            <div class="p-4 font-semibold">ONLINE — 2</div>
            <div class="flex-1 p-2 space-y-4 overflow-y-auto">
                <div class="flex items-center space-x-3">
                    <img src="https://randomuser.me/api/portraits/women/34.jpg" alt="Avatar" class="w-10 h-10 rounded-full">
                    <span class="font-semibold text-white">Jane Doe</span>
                </div>
                <div class="flex items-center space-x-3">
                    <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Avatar" class="w-10 h-10 rounded-full">
                    <span class="font-semibold text-white">John Doe</span>
                </div>
            </div>
        </div>
    </div>
</template>
