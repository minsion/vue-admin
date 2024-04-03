<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Users</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Account Settings</span>
            </li>
        </ul>
        <div class="pt-5">
            <div class="flex items-center justify-between mb-5">
                <h5 class="font-semibold text-lg dark:text-white-light">Settings</h5>
            </div>
            <TabGroup>
                <TabList class="flex font-semibold border-b border-[#ebedf2] dark:border-[#191e3a] mb-5 whitespace-nowrap overflow-y-auto">
                    <Tab as="template" v-slot="{ selected }">
                        <a
                            href="javascript:;"
                            class="flex gap-2 p-4 border-b border-transparent hover:border-primary hover:text-primary !outline-none"
                            :class="{ '!border-primary text-primary': selected }"
                        >
                            <icon-home />
                            Home
                        </a>
                    </Tab>
                    <Tab as="template" v-slot="{ selected }">
                        <a
                            href="javascript:;"
                            class="flex gap-2 p-4 border-b border-transparent hover:border-primary hover:text-primary !outline-none"
                            :class="{ '!border-primary text-primary': selected }"
                        >
                            <icon-dollar-sign-circle />
                            Payment Details
                        </a>
                    </Tab>
                    <Tab as="template" v-slot="{ selected }">
                        <a
                            href="javascript:;"
                            class="flex gap-2 p-4 border-b border-transparent hover:border-primary hover:text-primary !outline-none"
                            :class="{ '!border-primary text-primary': selected }"
                        >
                            <icon-user class="w-5 h-5" />
                            Preferences
                        </a>
                    </Tab>
                    <Tab as="template" v-slot="{ selected }">
                        <a
                            href="javascript:;"
                            class="flex gap-2 p-4 border-b border-transparent hover:border-primary hover:text-primary !outline-none"
                            :class="{ '!border-primary text-primary': selected }"
                        >
                            <icon-phone />
                            Danger Zone
                        </a>
                    </Tab>
                </TabList>
                <TabPanels>
                    <TabPanel>
                        <div>
                            <form class="border border-[#ebedf2] dark:border-[#191e3a] rounded-md p-4 mb-5 bg-white dark:bg-[#0e1726]">
                                <h6 class="text-lg font-bold mb-5">General Information</h6>
                                <div class="flex flex-col sm:flex-row">
                                    <div class="ltr:sm:mr-4 rtl:sm:ml-4 w-full sm:w-2/12 mb-5">
                                        <img src="/assets//images/profile-34.jpeg" alt="" class="w-20 h-20 md:w-32 md:h-32 rounded-full object-cover mx-auto" />
                                    </div>
                                    <div class="flex-1 grid grid-cols-1 sm:grid-cols-2 gap-5">
                                        <div>
                                            <label for="name">Full Name</label>
                                            <input id="name" type="text" placeholder="Jimmy Turner" class="form-input" />
                                        </div>
                                        <div>
                                            <label for="profession">Profession</label>
                                            <input id="profession" type="text" placeholder="Web Developer" class="form-input" />
                                        </div>
                                        <div>
                                            <label for="country">Country</label>
                                            <select id="country" class="form-select text-white-dark">
                                                <option>All Countries</option>
                                                <option selected>United States</option>
                                                <option>India</option>
                                                <option>Japan</option>
                                                <option>China</option>
                                                <option>Brazil</option>
                                                <option>Norway</option>
                                                <option>Canada</option>
                                            </select>
                                        </div>
                                        <div>
                                            <label for="address">Address</label>
                                            <input id="address" type="text" placeholder="New York" class="form-input" />
                                        </div>
                                        <div>
                                            <label for="location">Location</label>
                                            <input id="location" type="text" placeholder="Location" class="form-input" />
                                        </div>
                                        <div>
                                            <label for="phone">Phone</label>
                                            <input id="phone" type="text" placeholder="+1 (530) 555-12121" class="form-input" />
                                        </div>
                                        <div>
                                            <label for="email">Email</label>
                                            <input id="email" type="email" placeholder="Jimmy@gmail.com" class="form-input" />
                                        </div>
                                        <div>
                                            <label for="web">Website</label>
                                            <input id="web" type="text" placeholder="Enter URL" class="form-input" />
                                        </div>
                                        <div>
                                            <label class="inline-flex cursor-pointer">
                                                <input type="checkbox" class="form-checkbox" />
                                                <span class="text-white-dark relative checked:bg-none">Make this my default address</span>
                                            </label>
                                        </div>
                                        <div class="sm:col-span-2 mt-3">
                                            <button type="button" class="btn btn-primary">Save</button>
                                        </div>
                                    </div>
                                </div>
                            </form>
                            <form class="border border-[#ebedf2] dark:border-[#191e3a] rounded-md p-4 bg-white dark:bg-[#0e1726]">
                                <h6 class="text-lg font-bold mb-5">Social</h6>
                                <div class="grid grid-cols-1 sm:grid-cols-2 gap-5">
                                    <div class="flex">
                                        <div class="bg-[#eee] flex justify-center items-center rounded px-3 font-semibold dark:bg-[#1b2e4b] ltr:mr-2 rtl:ml-2">
                                            <icon-linkedin class="w-5 h-5" />
                                        </div>
                                        <input type="text" placeholder="jimmy_turner" class="form-input" />
                                    </div>
                                    <div class="flex">
                                        <div class="bg-[#eee] flex justify-center items-center rounded px-3 font-semibold dark:bg-[#1b2e4b] ltr:mr-2 rtl:ml-2">
                                            <icon-twitter class="w-5 h-5" />
                                        </div>
                                        <input type="text" placeholder="jimmy_turner" class="form-input" />
                                    </div>
                                    <div class="flex">
                                        <div class="bg-[#eee] flex justify-center items-center rounded px-3 font-semibold dark:bg-[#1b2e4b] ltr:mr-2 rtl:ml-2">
                                            <icon-facebook class="w-5 h-5" />
                                        </div>
                                        <input type="text" placeholder="jimmy_turner" class="form-input" />
                                    </div>
                                    <div class="flex">
                                        <div class="bg-[#eee] flex justify-center items-center rounded px-3 font-semibold dark:bg-[#1b2e4b] ltr:mr-2 rtl:ml-2">
                                            <icon-github />
                                        </div>
                                        <input type="text" placeholder="jimmy_turner" class="form-input" />
                                    </div>
                                </div>
                            </form>
                        </div>
                    </TabPanel>
                    <TabPanel>
                        <div>
                            <div class="grid grid-cols-1 lg:grid-cols-2 gap-5 mb-5">
                                <div class="panel">
                                    <div class="mb-5">
                                        <h5 class="font-semibold text-lg mb-4">Billing Address</h5>
                                        <p>
                                            Changes to your <span class="text-primary">Billing</span> information will take effect starting with scheduled
                                            payment and will be refelected on your next invoice.
                                        </p>
                                    </div>
                                    <div class="mb-5">
                                        <div class="border-b border-[#ebedf2] dark:border-[#1b2e4b]">
                                            <div class="flex items-start justify-between py-3">
                                                <h6 class="text-[#515365] font-bold dark:text-white-dark text-[15px]">
                                                    Address #1
                                                    <span class="block text-white-dark dark:text-white-light font-normal text-xs mt-1"
                                                        >2249 Caynor Circle, New Brunswick, New Jersey</span
                                                    >
                                                </h6>
                                                <div class="flex items-start justify-between ltr:ml-auto rtl:mr-auto">
                                                    <button class="btn btn-dark">Edit</button>
                                                </div>
                                            </div>
                                        </div>
                                        <div class="border-b border-[#ebedf2] dark:border-[#1b2e4b]">
                                            <div class="flex items-start justify-between py-3">
                                                <h6 class="text-[#515365] font-bold dark:text-white-dark text-[15px]">
                                                    Address #2
                                                    <span class="block text-white-dark dark:text-white-light font-normal text-xs mt-1"
                                                        >4262 Leverton Cove Road, Springfield, Massachusetts</span
                                                    >
                                                </h6>
                                                <div class="flex items-start justify-between ltr:ml-auto rtl:mr-auto">
                                                    <button class="btn btn-dark">Edit</button>
                                                </div>
                                            </div>
                                        </div>
                                        <div>
                                            <div class="flex items-start justify-between py-3">
                                                <h6 class="text-[#515365] font-bold dark:text-white-dark text-[15px]">
                                                    Address #3
                                                    <span class="block text-white-dark dark:text-white-light font-normal text-xs mt-1"
                                                        >2692 Berkshire Circle, Knoxville, Tennessee</span
                                                    >
                                                </h6>
                                                <div class="flex items-start justify-between ltr:ml-auto rtl:mr-auto">
                                                    <button class="btn btn-dark">Edit</button>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                    <button class="btn btn-primary">Add Address</button>
                                </div>
                                <div class="panel">
                                    <div class="mb-5">
                                        <h5 class="font-semibold text-lg mb-4">Payment History</h5>
                                        <p>
                                            Changes to your <span class="text-primary">Payment Method</span> information will take effect starting with
                                            scheduled payment and will be refelected on your next invoice.
                                        </p>
                                    </div>
                                    <div class="mb-5">
                                        <div class="border-b border-[#ebedf2] dark:border-[#1b2e4b]">
                                            <div class="flex items-start justify-between py-3">
                                                <div class="flex-none ltr:mr-4 rtl:ml-4">
                                                    <img src="/assets/images/card-americanexpress.svg" alt="" />
                                                </div>
                                                <h6 class="text-[#515365] font-bold dark:text-white-dark text-[15px]">
                                                    Mastercard
                                                    <span class="block text-white-dark dark:text-white-light font-normal text-xs mt-1"
                                                        >XXXX XXXX XXXX 9704</span
                                                    >
                                                </h6>
                                                <div class="flex items-start justify-between ltr:ml-auto rtl:mr-auto">
                                                    <button class="btn btn-dark">Edit</button>
                                                </div>
                                            </div>
                                        </div>
                                        <div class="border-b border-[#ebedf2] dark:border-[#1b2e4b]">
                                            <div class="flex items-start justify-between py-3">
                                                <div class="flex-none ltr:mr-4 rtl:ml-4">
                                                    <img src="/assets/images/card-mastercard.svg" alt="" />
                                                </div>
                                                <h6 class="text-[#515365] font-bold dark:text-white-dark text-[15px]">
                                                    American Express<span class="block text-white-dark dark:text-white-light font-normal text-xs mt-1"
                                                        >XXXX XXXX XXXX 310</span
                                                    >
                                                </h6>
                                                <div class="flex items-start justify-between ltr:ml-auto rtl:mr-auto">
                                                    <button class="btn btn-dark">Edit</button>
                                                </div>
                                            </div>
                                        </div>
                                        <div>
                                            <div class="flex items-start justify-between py-3">
                                                <div class="flex-none ltr:mr-4 rtl:ml-4">
                                                    <img src="/assets/images/card-visa.svg" alt="" />
                                                </div>
                                                <h6 class="text-[#515365] font-bold dark:text-white-dark text-[15px]">
                                                    Visa<span class="block text-white-dark dark:text-white-light font-normal text-xs mt-1"
                                                        >XXXX XXXX XXXX 5264</span
                                                    >
                                                </h6>
                                                <div class="flex items-start justify-between ltr:ml-auto rtl:mr-auto">
                                                    <button class="btn btn-dark">Edit</button>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                    <button class="btn btn-primary">Add Payment Method</button>
                                </div>
                            </div>
                            <div class="grid grid-cols-1 lg:grid-cols-2 gap-5">
                                <div class="panel">
                                    <div class="mb-5">
                                        <h5 class="font-semibold text-lg mb-4">Add Billing Address</h5>
                                        <p>Changes your New <span class="text-primary">Billing</span> Information.</p>
                                    </div>
                                    <div class="mb-5">
                                        <form>
                                            <div class="mb-5 grid grid-cols-1 sm:grid-cols-2 gap-4">
                                                <div>
                                                    <label for="billingName">Name</label>
                                                    <input id="billingName" type="text" placeholder="Enter Name" class="form-input" />
                                                </div>
                                                <div>
                                                    <label for="billingEmail">Email</label>
                                                    <input id="billingEmail" type="email" placeholder="Enter Email" class="form-input" />
                                                </div>
                                            </div>
                                            <div class="mb-5">
                                                <label for="billingAddress">Address</label>
                                                <input id="billingAddress" type="text" placeholder="Enter Address" class="form-input" />
                                            </div>
                                            <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-4 gap-4 mb-5">
                                                <div class="md:col-span-2">
                                                    <label for="billingCity">City</label>
                                                    <input id="billingCity" type="text" placeholder="Enter City" class="form-input" />
                                                </div>
                                                <div>
                                                    <label for="billingState">State</label>
                                                    <select id="billingState" class="form-select text-white-dark">
                                                        <option>Choose...</option>
                                                        <option>...</option>
                                                    </select>
                                                </div>
                                                <div>
                                                    <label for="billingZip">Zip</label>
                                                    <input id="billingZip" type="text" placeholder="Enter Zip" class="form-input" />
                                                </div>
                                            </div>
                                            <button type="button" class="btn btn-primary">Add</button>
                                        </form>
                                    </div>
                                </div>
                                <div class="panel">
                                    <div class="mb-5">
                                        <h5 class="font-semibold text-lg mb-4">Add Payment Method</h5>
                                        <p>Changes your New <span class="text-primary">Payment Method</span> Information.</p>
                                    </div>
                                    <div class="mb-5">
                                        <form>
                                            <div class="mb-5 grid grid-cols-1 sm:grid-cols-2 gap-4">
                                                <div>
                                                    <label for="payBrand">Card Brand</label>
                                                    <select id="payBrand" class="form-select text-white-dark">
                                                        <option selected>Mastercard</option>
                                                        <option>American Express</option>
                                                        <option>Visa</option>
                                                        <option>Discover</option>
                                                    </select>
                                                </div>
                                                <div>
                                                    <label for="payNumber">Card Number</label>
                                                    <input id="payNumber" type="text" placeholder="Card Number" class="form-input" />
                                                </div>
                                            </div>
                                            <div class="mb-5 grid grid-cols-1 sm:grid-cols-2 gap-4">
                                                <div>
                                                    <label for="payHolder">Holder Name</label>
                                                    <input id="payHolder" type="text" placeholder="Holder Name" class="form-input" />
                                                </div>
                                                <div>
                                                    <label for="payCvv">CVV/CVV2</label>
                                                    <input id="payCvv" type="text" placeholder="CVV" class="form-input" />
                                                </div>
                                            </div>
                                            <div class="mb-5 grid grid-cols-1 sm:grid-cols-2 gap-4">
                                                <div>
                                                    <label for="payExp">Card Expiry</label>
                                                    <input id="payExp" type="text" placeholder="Card Expiry" class="form-input" />
                                                </div>
                                            </div>
                                            <button type="button" class="btn btn-primary">Add</button>
                                        </form>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </TabPanel>
                    <TabPanel>
                        <div class="switch">
                            <div class="grid grid-cols-1 lg:grid-cols-2 gap-5 mb-5">
                                <div class="panel space-y-5">
                                    <h5 class="font-semibold text-lg mb-4">Choose Theme</h5>
                                    <div class="flex justify-around">
                                        <label class="inline-flex cursor-pointer">
                                            <input class="form-radio ltr:mr-4 rtl:ml-4 cursor-pointer" type="radio" name="flexRadioDefault" checked />
                                            <span>
                                                <img class="ms-3" width="100" height="68" alt="settings-dark" src="/assets/images/settings-light.svg" />
                                            </span>
                                        </label>

                                        <label class="inline-flex cursor-pointer">
                                            <input class="form-radio ltr:mr-4 rtl:ml-4 cursor-pointer" type="radio" name="flexRadioDefault" />
                                            <span>
                                                <img class="ms-3" width="100" height="68" alt="settings-light" src="/assets/images/settings-dark.svg" />
                                            </span>
                                        </label>
                                    </div>
                                </div>
                                <div class="panel space-y-5">
                                    <h5 class="font-semibold text-lg mb-4">Activity data</h5>
                                    <p>Download your Summary, Task and Payment History Data</p>
                                    <button type="button" class="btn btn-primary">Download Data</button>
                                </div>
                            </div>
                            <div class="grid grid-cols-1 md:grid-cols-3 gap-5">
                                <div class="panel space-y-5">
                                    <h5 class="font-semibold text-lg mb-4">Public Profile</h5>
                                    <p>Your <span class="text-primary">Profile</span> will be visible to anyone on the network.</p>
                                    <label class="w-12 h-6 relative">
                                        <input
                                            type="checkbox"
                                            class="custom_switch absolute w-full h-full opacity-0 z-10 cursor-pointer peer"
                                            id="custom_switch_checkbox1"
                                        />
                                        <span
                                            for="custom_switch_checkbox1"
                                            class="bg-[#ebedf2] dark:bg-dark block h-full rounded-full before:absolute before:left-1 before:bg-white dark:before:bg-white-dark dark:peer-checked:before:bg-white before:bottom-1 before:w-4 before:h-4 before:rounded-full peer-checked:before:left-7 peer-checked:bg-primary before:transition-all before:duration-300"
                                        ></span>
                                    </label>
                                </div>
                                <div class="panel space-y-5">
                                    <h5 class="font-semibold text-lg mb-4">Show my email</h5>
                                    <p>Your <span class="text-primary">Email</span> will be visible to anyone on the network.</p>
                                    <label class="w-12 h-6 relative">
                                        <input
                                            type="checkbox"
                                            class="custom_switch absolute w-full h-full opacity-0 z-10 cursor-pointer peer"
                                            id="custom_switch_checkbox2"
                                        />
                                        <span
                                            for="custom_switch_checkbox2"
                                            class="bg-[#ebedf2] dark:bg-dark block h-full rounded-full before:absolute before:left-1 before:bg-white dark:before:bg-white-dark dark:peer-checked:before:bg-white before:bottom-1 before:w-4 before:h-4 before:rounded-full peer-checked:before:left-7 peer-checked:bg-primary before:transition-all before:duration-300"
                                        ></span>
                                    </label>
                                </div>
                                <div class="panel space-y-5">
                                    <h5 class="font-semibold text-lg mb-4">Enable keyboard shortcuts</h5>
                                    <p>When enabled, press <span class="text-primary">ctrl</span> for help</p>
                                    <label class="w-12 h-6 relative">
                                        <input
                                            type="checkbox"
                                            class="custom_switch absolute w-full h-full opacity-0 z-10 cursor-pointer peer"
                                            id="custom_switch_checkbox3"
                                        />
                                        <span
                                            for="custom_switch_checkbox3"
                                            class="bg-[#ebedf2] dark:bg-dark block h-full rounded-full before:absolute before:left-1 before:bg-white dark:before:bg-white-dark dark:peer-checked:before:bg-white before:bottom-1 before:w-4 before:h-4 before:rounded-full peer-checked:before:left-7 peer-checked:bg-primary before:transition-all before:duration-300"
                                        ></span>
                                    </label>
                                </div>
                                <div class="panel space-y-5">
                                    <h5 class="font-semibold text-lg mb-4">Hide left navigation</h5>
                                    <p>Sidebar will be <span class="text-primary">hidden</span> by default</p>
                                    <label class="w-12 h-6 relative">
                                        <input
                                            type="checkbox"
                                            class="custom_switch absolute w-full h-full opacity-0 z-10 cursor-pointer peer"
                                            id="custom_switch_checkbox4"
                                        />
                                        <span
                                            for="custom_switch_checkbox4"
                                            class="bg-[#ebedf2] dark:bg-dark block h-full rounded-full before:absolute before:left-1 before:bg-white dark:before:bg-white-dark dark:peer-checked:before:bg-white before:bottom-1 before:w-4 before:h-4 before:rounded-full peer-checked:before:left-7 peer-checked:bg-primary before:transition-all before:duration-300"
                                        ></span>
                                    </label>
                                </div>
                                <div class="panel space-y-5">
                                    <h5 class="font-semibold text-lg mb-4">Advertisements</h5>
                                    <p>Display <span class="text-primary">Ads</span> on your dashboard</p>
                                    <label class="w-12 h-6 relative">
                                        <input
                                            type="checkbox"
                                            class="custom_switch absolute w-full h-full opacity-0 z-10 cursor-pointer peer"
                                            id="custom_switch_checkbox5"
                                        />
                                        <span
                                            for="custom_switch_checkbox5"
                                            class="bg-[#ebedf2] dark:bg-dark block h-full rounded-full before:absolute before:left-1 before:bg-white dark:before:bg-white-dark dark:peer-checked:before:bg-white before:bottom-1 before:w-4 before:h-4 before:rounded-full peer-checked:before:left-7 peer-checked:bg-primary before:transition-all before:duration-300"
                                        ></span>
                                    </label>
                                </div>
                                <div class="panel space-y-5">
                                    <h5 class="font-semibold text-lg mb-4">Social Profile</h5>
                                    <p>Enable your <span class="text-primary">social</span> profiles on this network</p>
                                    <label class="w-12 h-6 relative">
                                        <input
                                            type="checkbox"
                                            class="custom_switch absolute w-full h-full opacity-0 z-10 cursor-pointer peer"
                                            id="custom_switch_checkbox6"
                                        />
                                        <span
                                            for="custom_switch_checkbox6"
                                            class="bg-[#ebedf2] dark:bg-dark block h-full rounded-full before:absolute before:left-1 before:bg-white dark:before:bg-white-dark dark:peer-checked:before:bg-white before:bottom-1 before:w-4 before:h-4 before:rounded-full peer-checked:before:left-7 peer-checked:bg-primary before:transition-all before:duration-300"
                                        ></span>
                                    </label>
                                </div>
                            </div>
                        </div>
                    </TabPanel>
                    <TabPanel>
                        <div class="switch">
                            <div class="grid grid-cols-1 md:grid-cols-3 gap-5">
                                <div class="panel space-y-5">
                                    <h5 class="font-semibold text-lg mb-4">Purge Cache</h5>
                                    <p>Remove the active resource from the cache without waiting for the predetermined cache expiry time.</p>
                                    <button class="btn btn-secondary">Clear</button>
                                </div>
                                <div class="panel space-y-5">
                                    <h5 class="font-semibold text-lg mb-4">Deactivate Account</h5>
                                    <p>You will not be able to receive messages, notifications for up to 24 hours.</p>
                                    <label class="w-12 h-6 relative">
                                        <input
                                            type="checkbox"
                                            class="custom_switch absolute w-full h-full opacity-0 z-10 cursor-pointer peer"
                                            id="custom_switch_checkbox7"
                                        />
                                        <span
                                            for="custom_switch_checkbox7"
                                            class="bg-[#ebedf2] dark:bg-dark block h-full rounded-full before:absolute before:left-1 before:bg-white dark:before:bg-white-dark dark:peer-checked:before:bg-white before:bottom-1 before:w-4 before:h-4 before:rounded-full peer-checked:before:left-7 peer-checked:bg-primary before:transition-all before:duration-300"
                                        ></span>
                                    </label>
                                </div>
                                <div class="panel space-y-5">
                                    <h5 class="font-semibold text-lg mb-4">Delete Account</h5>
                                    <p>Once you delete the account, there is no going back. Please be certain.</p>
                                    <button class="btn btn-danger btn-delete-account">Delete my account</button>
                                </div>
                            </div>
                        </div>
                    </TabPanel>
                </TabPanels>
            </TabGroup>
        </div>
    </div>
</template>
<script lang="ts" setup>
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
    import { useAppStore } from '@/stores/index';
    import { useMeta } from '@/composables/use-meta';

    import IconHome from '@/components/icon/icon-home.vue';
    import IconDollarSignCircle from '@/components/icon/icon-dollar-sign-circle.vue';
    import IconUser from '@/components/icon/icon-user.vue';
    import IconPhone from '@/components/icon/icon-phone.vue';
    import IconLinkedin from '@/components/icon/icon-linkedin.vue';
    import IconTwitter from '@/components/icon/icon-twitter.vue';
    import IconFacebook from '@/components/icon/icon-facebook.vue';
    import IconGithub from '@/components/icon/icon-github.vue';

    useMeta({ title: 'Account Setting' });
    const store = useAppStore();
</script>
