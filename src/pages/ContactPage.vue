<script setup>
import Page from "../components/Page.vue";
</script>

<template>
    <Page class="grid gap-5 text-[13px]/[1.2] tracking-[-0.45px]">
        <section class="grid gap-2.5">
            <h1>Контакты</h1>
            <p class="text-(--dim)">У нас вы можете купить модульный дом в ипотеку</p>
        </section>

        <section class="grid gap-2.5">
            <div class="flex items-center gap-5 bg-[#F9F9F9] rounded-[15px] p-4">
                <img src="/images/call.svg" width="24" alt="">

                <div>
                    <div class="text-[14px]/[22px] text-[#384040] font-semibold">Телефон для связи:</div>
                    <div class="text-[12px]/[16px]">8 (343) 213-06-05</div>
                </div>
            </div>

            <div class="flex items-center gap-5 bg-[#F9F9F9] rounded-[15px] p-4">
                <img src="/images/email.svg" width="24" alt="">

                <div>
                    <div class="text-[14px]/[22px] text-[#384040] font-semibold">Напишите нам:</div>
                    <div class="text-[12px]/[16px]">mody.linfo@gmail.com</div>
                </div>
            </div>

            <div class="flex items-center gap-5 bg-[#F9F9F9] rounded-[15px] p-4">
                <img src="/images/clock.svg" width="24" alt="">

                <div>
                    <div class="text-[14px]/[22px] text-[#384040] font-semibold">График работы:</div>
                    <div class="text-[12px]/[16px]">Пн-сб: с 09:00 до 19:00</div>
                </div>
            </div>

            <div class="flex items-center gap-5 bg-[#F9F9F9] rounded-[15px] p-4">
                <img src="/images/location.svg" width="24" alt="">

                <div>
                    <div class="text-[14px]/[22px] text-[#384040] font-semibold">Адрес:</div>
                    <div class="text-[12px]/[16px]">62000 Свердловская область, г. Екатеринбург, ул. 40 летия Комсомола, д. 32в, офис 319</div>
                </div>
            </div>
        </section>
    </Page>
</template>

<style scoped>

</style>
