<script setup>
    import { ref,computed } from 'vue';
    const name = ref("Nazmul Hossain");
    const phone = ref("01858734951");
    const email = ref("hossainnazmul191@gmail.com");
    const gender = ref("Male");
    const image  = ref("https://plus.unsplash.com/premium_photo-1683910767532-3a25b821f7ae?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=50&q=40");
    const birthday = ref("Jan 01, 1997");
    const description = ref("This is user profile description page");
    const age = ref(20);

    const birthYear = computed(()=>{
        const currentYear = new Date().getFullYear();
        const YearOfBirth = currentYear - age.value;
        return YearOfBirth;
    })
    const legalAge = computed(()=>{
        return (age.value > 18)? true : false;
    })
</script>

<template>
        
    <div class="">
        <div class="w-full text-white bg-main-color">
            <div x-data="{ open: false }"
                class="flex flex-col max-w-screen-xl px-4 mx-auto md:items-center md:justify-between md:flex-row md:px-6 lg:px-8">
                <div class="p-4 flex flex-row items-center justify-between">
                    <a href="#"
                        class="text-lg font-semibold tracking-widest uppercase rounded-lg focus:outline-none focus:shadow-outline">example
                        profile</a>
                    <button class="md:hidden rounded-lg focus:outline-none focus:shadow-outline" @click="open = !open">
                        <svg fill="currentColor" viewBox="0 0 20 20" class="w-6 h-6">
                            <path x-show="!open" fill-rule="evenodd"
                                d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM9 15a1 1 0 011-1h6a1 1 0 110 2h-6a1 1 0 01-1-1z"
                                clip-rule="evenodd"></path>
                            <path x-show="open" fill-rule="evenodd"
                                d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                                clip-rule="evenodd"></path>
                        </svg>
                    </button>
                </div>
                <nav :class="{'flex': open, 'hidden': !open}"
                    class="flex-col flex-grow pb-4 md:pb-0 hidden md:flex md:justify-end md:flex-row">
                    <div @click.away="open = false" class="relative" x-data="{ open: false }">
                        <button @click="open = !open"
                            class="flex flex-row items-center space-x-2 w-full px-4 py-2 mt-2 text-sm font-semibold text-left bg-transparent hover:bg-blue-800 md:w-auto md:inline md:mt-0 md:ml-4 hover:bg-gray-200 focus:bg-blue-800 focus:outline-none focus:shadow-outline">
                            <span>Jane Doe</span>
                            <img class="inline h-6 rounded-full"
                                src="https://avatars2.githubusercontent.com/u/24622175?s=60&amp;v=4">
                            <svg fill="currentColor" viewBox="0 0 20 20" :class="{'rotate-180': open, 'rotate-0': !open}"
                                class="inline w-4 h-4 transition-transform duration-200 transform">
                                <path fill-rule="evenodd"
                                    d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                                    clip-rule="evenodd"></path>
                            </svg>
                        </button>
                        <div x-show="open" x-transition:enter="transition ease-out duration-100"
                            x-transition:enter-start="transform opacity-0 scale-95"
                            x-transition:enter-end="transform opacity-100 scale-100"
                            x-transition:leave="transition ease-in duration-75"
                            x-transition:leave-start="transform opacity-100 scale-100"
                            x-transition:leave-end="transform opacity-0 scale-95"
                            class="absolute right-0 w-full mt-2 origin-top-right rounded-md shadow-lg md:w-48">
                            <!-- <div class="py-2 bg-white text-blue-800 text-sm rounded-sm border border-main-color shadow-sm">
                                <a class="block px-4 py-2 mt-2 text-sm bg-white md:mt-0 focus:text-gray-900 hover:bg-indigo-100 focus:bg-gray-200 focus:outline-none focus:shadow-outline"
                                    href="#">Settings</a>
                                <a class="block px-4 py-2 mt-2 text-sm bg-white md:mt-0 focus:text-gray-900 hover:bg-indigo-100 focus:bg-gray-200 focus:outline-none focus:shadow-outline"
                                    href="#">Help</a>
                                <div class="border-b"></div>
                                <a class="block px-4 py-2 mt-2 text-sm bg-white md:mt-0 focus:text-gray-900 hover:bg-indigo-100 focus:bg-gray-200 focus:outline-none focus:shadow-outline"
                                    href="#">Logout</a>
                            </div> -->
                        </div>
                    </div>
                </nav>
            </div>
        </div>
        <!-- End of Navbar -->
    
        <div class="container mx-auto my-5 p-5">
            <div class="md:flex no-wrap md:-mx-2">
                <!-- Left Side -->
            
                <!-- Right Side -->
                <div class="w-full md:w-9/12 mx-2 h-64">
                    <!-- Profile tab -->
                    <!-- About Section -->
                    <div class="bg-gray-100 p-3 shadow-sm rounded-sm">
                        <div class="flex items-center space-x-2 font-semibold text-gray-900 leading-8">
                            <span clas="text-green-500">
                                <svg class="h-5" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                                    stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                        d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
                                </svg>
                            </span>
                            <span class="tracking-wide">Profile Details</span>
                        </div>
                        <div class="text-gray-700">
                            <div class="grid md:grid-cols-2 text-sm">
                                <div class="grid grid-cols-2">
                                    <div class="px-4 py-2 font-semibold">Name</div>
                                    <div class="px-4 py-2">{{ name }}</div>
                                </div>
                                <div class="grid grid-cols-2">
                                    <div class="px-4 py-2 font-semibold">Gender</div>
                                    <div class="px-4 py-2">{{gender}}</div>
                                </div>
                                <div class="grid grid-cols-2">
                                    <div class="px-4 py-2 font-semibold">Contact No.</div>
                                    <div class="px-4 py-2">{{phone}}</div>
                                </div>
                                <div class="grid grid-cols-2">
                                    <div class="px-4 py-2 font-semibold">Image</div>
                                    <div class="px-4 py-2">
                                         <img :src="image" alt="">
                                    </div>
                                </div>
                                <div class="grid grid-cols-2">
                                    <div class="px-4 py-2 font-semibold">Email</div>
                                    <div class="px-4 py-2">
                                        <a class="text-blue-800" :href="email">{{email}}</a>
                                    </div>
                                </div>
                                <div class="grid grid-cols-2">
                                    <div class="px-4 py-2 font-semibold">Birthday</div>
                                    <div class="px-4 py-2">{{ birthday }}</div>
                                </div>
                                <div class="grid grid-cols-2">
                                    <div class="px-4 py-2 font-semibold">description</div>
                                    <div class="px-4 py-2">{{ description }}</div>
                                </div>
                                <div class="grid grid-cols-2">
                                    <div class="px-4 py-2 font-semibold">Birth Year</div>
                                    <div class="px-4 py-2">{{ birthYear }}</div>
                                </div>
                                <div class="grid grid-cols-2">
                                    <div class="px-4 py-2 font-semibold">Legal Age</div>
                                    <div class="px-4 py-2">He is {{age}} years old. <span v-if="legalAge" class="inline-flex items-center rounded-md bg-green-50 px-2 py-1 text-xs font-medium text-green-700 ring-1 ring-inset ring-green-600/20">He is eligible for the vote</span><span class="inline-flex items-center rounded-md bg-red-50 px-2 py-1 text-xs font-medium text-red-700 ring-1 ring-inset ring-red-600/10" v-else="">He is not eligible for the vote</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <!-- End of about section -->
    
                    <div class="my-4"></div>
    
                    <!-- Experience and education -->
                    <div class="p-3 shadow-sm rounded-sm bg-gray-100">
    
                        <div class="grid grid-cols-2">
                            <div>
                                <div class="flex items-center space-x-2 font-semibold text-gray-900 leading-8 mb-3"> 
                                    <span class="tracking-wide">Edit Profile Details</span>
                                </div>
                                <ul class="list-inside space-y-2">
                                    <li>
                                        <div class="text-black-600">Name</div>
                                        <div class="text-gray-500 text-xs">
                                            <input type="text" class="border border-white-300 rounded-md p-2 w-9/12" v-model="name"/>
                                        </div>
                                    </li>
                                    <li>
                                        <div class="text-black-600">Phone</div>
                                        <div class="text-gray-500 text-xs">
                                            <input type="text" class="border border-white-300 rounded-md p-2 w-9/12" v-model="phone"/>
                                        </div>
                                    </li>
                                    <li>
                                        <div class="text-black-600">Email</div>
                                        <div class="text-gray-500 text-xs">
                                            <input type="text" class="border border-white-300 rounded-md p-2 w-9/12" v-model="email"/>
                                        </div>
                                    </li>
                                    <li>
                                        <div class="text-black-600">Gender</div>
                                        <div class="text-gray-500 text-xs">
                                            <input type="text" class="border border-white-300 rounded-md p-2 w-9/12" v-model="gender"/>
                                        </div>
                                    </li>
                                </ul>
                            </div>
                            <div>
                               
                                <ul class="list-inside space-y-2">
                                    <li>
                                        <div class="text-black-600">Image</div>
                                        <div class="text-gray-500 text-xs">
                                            <input type="file" class="border border-white-300 rounded-md p-2 w-9/12"/>
                                        </div>
                                    </li>
                                    <li>
                                        <div class="text-black-600">Date of birth</div>
                                        <div class="text-gray-500 text-xs">
                                            <input type="date" class="border border-white-300 rounded-md p-2 w-9/12" v-model="birthday"/>
                                        </div>
                                    </li>
                                    <li>
                                        <div class="text-black-600">Age</div>
                                        <div class="text-gray-500 text-xs">
                                            <input type="number" class="border border-white-300 rounded-md p-2 w-9/12" v-model="age"/>
                                        </div>
                                    </li>
                                    <li>
                                        <div class="text-black-600">Description</div>
                                        <div class="text-gray-500 text-xs">
                                            <textarea type="text" class="border border-white-300 rounded-md p-2 w-9/12" v-model="description" cols="30" rows="5"></textarea>
                                            
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <!-- End of Experience and education grid -->
                    </div>
                    <!-- End of profile tab -->
                </div>
            </div>
        </div>
    </div>

</template>

<style scoped>
   
</style>
