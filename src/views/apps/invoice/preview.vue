<template>
    <div>
        <div class="flex items-center lg:justify-end justify-center flex-wrap gap-4 mb-6">
            <button type="button" class="btn btn-info gap-2">
                <icon-send />
                Send Invoice
            </button>

            <button type="button" class="btn btn-primary gap-2" @click="print">
                <icon-printer />

                Print
            </button>

            <button type="button" class="btn btn-success gap-2">
                <icon-download />
                Download
            </button>

            <router-link to="/apps/invoice/add" class="btn btn-secondary gap-2">
                <icon-plus />
                Create
            </router-link>

            <router-link to="/apps/invoice/edit" class="btn btn-warning gap-2">
                <icon-edit />
                Edit
            </router-link>
        </div>
        <div class="panel">
            <div class="flex justify-between flex-wrap gap-4 px-4">
                <div class="text-2xl font-semibold uppercase">Invoice</div>
                <div class="shrink-0">
                    <img src="/assets/images/logo.svg" alt="" class="w-14 ltr:ml-auto rtl:mr-auto" />
                </div>
            </div>
            <div class="ltr:text-right rtl:text-left px-4">
                <div class="space-y-1 mt-6 text-white-dark">
                    <div>13 Tetrick Road, Cypress Gardens, Florida, 33884, US</div>
                    <div>vristo@gmail.com</div>
                    <div>+1 (070) 123-4567</div>
                </div>
            </div>

            <hr class="border-[#e0e6ed] dark:border-[#1b2e4b] my-6" />
            <div class="flex justify-between lg:flex-row flex-col gap-6 flex-wrap">
                <div class="flex-1">
                    <div class="space-y-1 text-white-dark">
                        <div>Issue For:</div>
                        <div class="text-black dark:text-white font-semibold">John Doe</div>
                        <div>405 Mulberry Rd. Mc Grady, NC, 28649</div>
                        <div>redq@company.com</div>
                        <div>(128) 666 070</div>
                    </div>
                </div>
                <div class="flex justify-between sm:flex-row flex-col gap-6 lg:w-2/3">
                    <div class="xl:1/3 lg:w-2/5 sm:w-1/2">
                        <div class="flex items-center w-full justify-between mb-2">
                            <div class="text-white-dark">Invoice :</div>
                            <div>#8701</div>
                        </div>
                        <div class="flex items-center w-full justify-between mb-2">
                            <div class="text-white-dark">Issue Date :</div>
                            <div>13 Sep 2022</div>
                        </div>
                        <div class="flex items-center w-full justify-between mb-2">
                            <div class="text-white-dark">Order ID :</div>
                            <div>#OD-85794</div>
                        </div>
                        <div class="flex items-center w-full justify-between">
                            <div class="text-white-dark">Shipment ID :</div>
                            <div>#SHP-8594</div>
                        </div>
                    </div>
                    <div class="xl:1/3 lg:w-2/5 sm:w-1/2">
                        <div class="flex items-center w-full justify-between mb-2">
                            <div class="text-white-dark">Bank Name:</div>
                            <div class="whitespace-nowrap">Bank Of America</div>
                        </div>
                        <div class="flex items-center w-full justify-between mb-2">
                            <div class="text-white-dark">Account Number:</div>
                            <div>1234567890</div>
                        </div>
                        <div class="flex items-center w-full justify-between mb-2">
                            <div class="text-white-dark">SWIFT Code:</div>
                            <div>S58K796</div>
                        </div>
                        <div class="flex items-center w-full justify-between mb-2">
                            <div class="text-white-dark">IBAN:</div>
                            <div>L5698445485</div>
                        </div>
                        <div class="flex items-center w-full justify-between mb-2">
                            <div class="text-white-dark">Country:</div>
                            <div>United States</div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="table-responsive mt-6">
                <table class="table-striped">
                    <thead>
                        <tr>
                            <template v-for="item in columns" :key="item.key">
                                <th :class="[item.class]">{{ item.label }}</th>
                            </template>
                        </tr>
                    </thead>
                    <tbody>
                        <template v-for="item in items" :key="item.id">
                            <tr>
                                <td>{{ item.id }}</td>
                                <td>{{ item.title }}</td>
                                <td>{{ item.quantity }}</td>
                                <td class="ltr:text-right rtl:text-left">${{ item.price }}</td>
                                <td class="ltr:text-right rtl:text-left">${{ item.amount }}</td>
                            </tr>
                        </template>
                    </tbody>
                </table>
            </div>
            <div class="grid sm:grid-cols-2 grid-cols-1 px-4 mt-6">
                <div></div>
                <div class="ltr:text-right rtl:text-left space-y-2">
                    <div class="flex items-center">
                        <div class="flex-1">Subtotal</div>
                        <div class="w-[37%]">$3255</div>
                    </div>
                    <div class="flex items-center">
                        <div class="flex-1">Tax</div>
                        <div class="w-[37%]">$700</div>
                    </div>
                    <div class="flex items-center">
                        <div class="flex-1">Shipping Rate</div>
                        <div class="w-[37%]">$0</div>
                    </div>
                    <div class="flex items-center">
                        <div class="flex-1">Discount</div>
                        <div class="w-[37%]">$10</div>
                    </div>
                    <div class="flex items-center font-semibold text-lg">
                        <div class="flex-1">Grand Total</div>
                        <div class="w-[37%]">$3945</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts" setup>
    import { ref } from 'vue';
    import { useMeta } from '@/composables/use-meta';

    import IconSend from '@/components/icon/icon-send.vue';
    import IconPrinter from '@/components/icon/icon-printer.vue';
    import IconDownload from '@/components/icon/icon-download.vue';
    import IconPlus from '@/components/icon/icon-plus.vue';
    import IconEdit from '@/components/icon/icon-edit.vue';


    useMeta({ title: 'Invoice Preview' });

    const items = ref([
        {
            id: 1,
            title: 'Calendar App Customization',
            quantity: 1,
            price: '120',
            amount: '120',
        },
        {
            id: 2,
            title: 'Chat App Customization',
            quantity: 1,
            price: '230',
            amount: '230',
        },
        {
            id: 3,
            title: 'Laravel Integration',
            quantity: 1,
            price: '405',
            amount: '405',
        },
        {
            id: 4,
            title: 'Backend UI Design',
            quantity: 1,
            price: '2500',
            amount: '2500',
        },
    ]);
    const columns = ref([
        {
            key: 'id',
            label: 'S.NO',
        },
        {
            key: 'title',
            label: 'ITEMS',
        },
        {
            key: 'quantity',
            label: 'QTY',
        },
        {
            key: 'price',
            label: 'PRICE',
            class: 'ltr:text-right rtl:text-left',
        },
        {
            key: 'amount',
            label: 'AMOUNT',
            class: 'ltr:text-right rtl:text-left',
        },
    ]);

    const print = () => {
        window.print();
    };
</script>
