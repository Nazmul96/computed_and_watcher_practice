<script setup>
    import { ref,computed,watch } from 'vue';
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

    watch(age, (oldAge, newAge)=>{
        age.value = newAge;
    })
    const legalAge = computed(()=>{
        return (age.value > 18)? true : false;
    })
</script>

<template>
        
    <div class="mb-10">
      
    
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
                                    <div class="px-4 py-2"><span class="inline-flex items-center rounded-md bg-green-50 px-2 py-1 text-xs font-medium text-green-700 ring-1 ring-inset ring-green-600/20">{{ birthYear }}</span></div>
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
