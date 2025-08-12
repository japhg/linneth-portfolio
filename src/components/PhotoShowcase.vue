<template>
    <div class="w-full">
        <div class="flex flex-col justify-start gap-5 text-center mb-8">
            <h2 class="text-subHeading">Photo Showcase</h2>

            <p class="text-content">
                Explore Linneth's stunning photography collection, capturing moments of beauty,
                creativity, travel experiences and inspiration.
            </p>
        </div>

        <!-- Photo Grid -->
        <div class="w-full">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-4 max-w-4xl mx-auto">
                <!-- Left Column -->
                <div class="flex flex-col gap-4">
                    <div
                        class="bg-gray-200 rounded-lg overflow-hidden aspect-[3/4]"
                        data-aos="fade-up"
                        :data-aos-delay="200"
                        data-aos-duration="600"
                    >
                        <img src="/images/2.jpg" alt="" class="w-full h-full object-cover" />
                    </div>

                    <div
                        class="bg-gray-200 rounded-lg overflow-hidden aspect-[4/3]"
                        data-aos="fade-up"
                        :data-aos-delay="400"
                        data-aos-duration="600"
                    >
                        <img src="/images/4.jpg" alt="" class="w-full h-full object-cover" />
                    </div>
                </div>

                <!-- Right Column -->
                <div class="flex flex-col gap-4">
                    <div
                        class="bg-gray-200 rounded-lg overflow-hidden aspect-[4/3]"
                        data-aos="fade-up"
                        :data-aos-delay="600"
                        data-aos-duration="600"
                    >
                        <img src="/images/5.jpg" alt="" class="w-full h-full object-cover" />
                    </div>

                    <div
                        class="bg-gray-200 rounded-lg overflow-hidden aspect-[3/4]"
                        data-aos="fade-up"
                        :data-aos-delay="800"
                        data-aos-duration="600"
                    >
                        <img src="/images/3.jpg" alt="" class="w-full h-full object-cover" />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
