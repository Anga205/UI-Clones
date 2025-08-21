<script>
    import '../styles/tailwind.css';

    // Mock data for stories and posts
    const stories = [
        { id: 1, user: 'sveltejs', avatar: 'https://pbs.twimg.com/profile_images/1121395911849062400/7_Ihe2YJ_400x400.png' },
        { id: 2, user: 'tailwindcss', avatar: 'https://pbs.twimg.com/profile_images/1468993891584024576/p0L__12s_400x400.jpg' },
        { id: 3, user: 'github', avatar: 'https://pbs.twimg.com/profile_images/1414990564408262661/r6YemvF9_400x400.jpg' },
        { id: 4, user: 'vercel', avatar: 'https://pbs.twimg.com/profile_images/1253318092648456192/9k206p56_400x400.jpg' },
        { id: 5, user: 'vite', avatar: 'https://pbs.twimg.com/profile_images/1474802394039078913/5FGzz_3N_400x400.jpg' },
        { id: 6, user: 'devdojo', avatar: 'https://pbs.twimg.com/profile_images/1598011983282425856/i4prp_m5_400x400.jpg' },
        { id: 7, user: 'freecodecamp', avatar: 'https://pbs.twimg.com/profile_images/1276770212927410176/qTgTIejk_400x400.jpg' }
    ];

    const posts = [
        {
            id: 1,
            user: 'sveltejs',
            avatar: 'https://pbs.twimg.com/profile_images/1121395911849062400/7_Ihe2YJ_400x400.png',
            image: 'https://images.unsplash.com/photo-1633356122544-f134324a6cee?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80',
            caption: 'Svelte makes building web apps a breeze. What are you building?',
            likes: 1337,
            comments: 42
        },
        {
            id: 2,
            user: 'tailwindcss',
            avatar: 'https://pbs.twimg.com/profile_images/1468993891584024576/p0L__12s_400x400.jpg',
            image: 'https://images.unsplash.com/photo-1555099962-4199c345e546?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80',
            caption: 'Rapidly build modern websites without ever leaving your HTML.',
            likes: 2048,
            comments: 99
        }
    ];
</script>

<div class="bg-gray-50 min-h-screen font-sans">
    <!-- Header -->
    <header class="fixed top-0 left-0 right-0 bg-white border-b border-gray-300 z-10">
        <div class="flex items-center justify-between max-w-5xl mx-auto px-4 py-2">
            <!-- Logo -->
            <h1 class="text-2xl font-serif font-bold">Instagram</h1>

            <!-- Search -->
            <div class="hidden sm:block w-64">
                <input type="text" placeholder="Search" class="bg-gray-100 border border-gray-300 rounded-md w-full px-3 py-1 text-sm focus:outline-none focus:ring-1 focus:ring-gray-400" />
            </div>

            <!-- Icons -->
            <div class="flex items-center space-x-5">
                <!-- Home Icon -->
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 cursor-pointer" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" /></svg>
                <!-- Messenger Icon -->
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 cursor-pointer" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M17 8h2a2 2 0 012 2v6a2 2 0 01-2 2h-2v4l-4-4H9a2 2 0 01-2-2V7a2 2 0 012-2h2.586a1 1 0 01.707.293l2.414 2.414a1 1 0 00.707.293H17z" /></svg>
                <!-- Add Post Icon -->
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 cursor-pointer" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M12 9v3m0 0v3m0-3h3m-3 0H9m12 0a9 9 0 11-18 0 9 9 0 0118 0z" /></svg>
                <!-- Profile Avatar -->
                <img src="https://i.pravatar.cc/150?u=a042581f4e29026704d" alt="profile" class="h-6 w-6 rounded-full cursor-pointer" />
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="pt-20 max-w-5xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-8 px-4">
        <!-- Left Column (Feed) -->
        <div class="md:col-span-2">
            <!-- Stories -->
            <div class="bg-white border border-gray-300 rounded-lg p-4 mb-6">
                <div class="flex space-x-4 overflow-x-auto">
                    {#each stories as story}
                        <div class="flex-shrink-0 text-center">
                            <div class="w-16 h-16 rounded-full p-0.5 bg-gradient-to-r from-yellow-400 via-red-500 to-pink-500">
                                <img class="w-full h-full rounded-full object-cover border-2 border-white" src={story.avatar} alt={story.user} />
                            </div>
                            <p class="text-xs mt-1 truncate w-16">{story.user}</p>
                        </div>
                    {/each}
                </div>
            </div>

            <!-- Posts -->
            <div class="space-y-6">
                {#each posts as post}
                    <div class="bg-white border border-gray-300 rounded-lg">
                        <!-- Post Header -->
                        <div class="flex items-center p-3">
                            <img src={post.avatar} alt={post.user} class="h-8 w-8 rounded-full object-cover" />
                            <p class="font-semibold ml-3 text-sm">{post.user}</p>
                            <button class="ml-auto text-gray-500" aria-label="More options">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M5 12h.01M12 12h.01M19 12h.01M6 12a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0z" /></svg>
                            </button>
                        </div>

                        <!-- Post Image -->
                        <img src={post.image} alt="Post" class="w-full" />

                        <!-- Post Actions -->
                        <div class="p-4">
                            <div class="flex items-center space-x-4 mb-2">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-7 w-7 cursor-pointer hover:text-gray-500" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z" /></svg>
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-7 w-7 cursor-pointer hover:text-gray-500" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z" /></svg>
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-7 w-7 cursor-pointer hover:text-gray-500" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8" /></svg>
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-7 w-7 cursor-pointer hover:text-gray-500 ml-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"><path stroke-linecap="round" stroke-linejoin="round" d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z" /></svg>
                            </div>

                            <!-- Likes and Caption -->
                            <p class="font-semibold text-sm">{post.likes.toLocaleString()} likes</p>
                            <p class="text-sm mt-1">
                                <span class="font-semibold">{post.user}</span>
                                {post.caption}
                            </p>

                            <!-- Comments -->
                            <p class="text-gray-500 text-sm mt-2 cursor-pointer">View all {post.comments} comments</p>
                            <div class="mt-2 border-t border-gray-200 pt-2">
                                <input type="text" placeholder="Add a comment..." class="w-full text-sm outline-none bg-transparent" />
                            </div>
                        </div>
                    </div>
                {/each}
            </div>
        </div>

        <!-- Right Column (Sidebar) -->
        <div class="hidden md:block">
            <div class="fixed w-72">
                <div class="flex items-center mb-6">
                    <img src="https://i.pravatar.cc/150?u=a042581f4e29026704d" alt="profile" class="h-14 w-14 rounded-full" />
                    <div class="ml-4">
                        <p class="font-semibold text-sm">your_username</p>
                        <p class="text-gray-500 text-sm">Your Name</p>
                    </div>
                    <button class="ml-auto text-blue-500 font-semibold text-xs">Switch</button>
                </div>

                <div class="flex justify-between items-center mb-4">
                    <p class="font-semibold text-gray-500 text-sm">Suggestions For You</p>
                    <button class="font-semibold text-xs">See All</button>
                </div>

                <div class="space-y-4">
                    {#each stories.slice(0, 5) as suggestion}
                        <div class="flex items-center">
                            <img src={suggestion.avatar} alt={suggestion.user} class="h-8 w-8 rounded-full" />
                            <div class="ml-3">
                                <p class="font-semibold text-sm">{suggestion.user}</p>
                                <p class="text-gray-400 text-xs">Suggested for you</p>
                            </div>
                            <button class="ml-auto text-blue-500 font-semibold text-xs">Follow</button>
                        </div>
                    {/each}
                </div>

                <div class="text-xs text-gray-300 mt-8">
                    <p>About · Help · Press · API · Jobs · Privacy · Terms · Locations · Language</p>
                    <p class="mt-4">© 2023 INSTAGRAM FROM META</p>
                </div>
            </div>
        </div>
    </main>
</div>
