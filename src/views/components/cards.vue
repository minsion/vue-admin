<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Components</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Cards</span>
            </li>
        </ul>
        <div class="pt-5 grid grid-cols-1 lg:grid-cols-2 gap-6">
            <!-- Card 1 -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Card 1</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code1')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5 flex items-center justify-center">
                    <div
                        class="max-w-[19rem] w-full bg-white shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none"
                    >
                        <div class="py-7 px-6">
                            <div class="bg-[#3b3f5c] mb-5 inline-block p-3 text-[#f1f2f3] rounded-full">
                                <icon-droplet />
                            </div>
                            <h5 class="text-[#3b3f5c] text-xl font-semibold mb-4 dark:text-white-light">Simple</h5>
                            <p class="text-white-dark">Mauris nisi felis, placerat in volutpat id, varius et sapien.</p>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code1')">
                    <highlight>
                        <pre>
&lt;!-- card 1 --&gt;
&lt;div class=&quot;max-w-[19rem] w-full bg-white shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none&quot;&gt;
  &lt;div class=&quot;py-7 px-6&quot;&gt;
    &lt;div class=&quot;bg-[#3b3f5c] mb-5 inline-block p-3 text-[#f1f2f3] rounded-full&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/div&gt;
    &lt;h5 class=&quot;text-[#3b3f5c] text-xl font-semibold mb-4 dark:text-white-light&quot;&gt;Simple&lt;/h5&gt;
    &lt;p class=&quot;text-white-dark&quot;&gt;Mauris nisi felis, placerat in volutpat id, varius et sapien.&lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Card 2 -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Card 2</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code2')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5 flex items-center justify-center">
                    <div
                        class="max-w-[19rem] w-full bg-white shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none"
                    >
                        <div class="py-7 px-6">
                            <div class="-mt-7 mb-7 -mx-6 rounded-tl rounded-tr h-[215px] overflow-hidden">
                                <img src="/assets/images/profile-28.jpeg" alt="" class="w-full h-full object-cover" />
                            </div>
                            <h5 class="text-[#3b3f5c] text-xl font-semibold mb-4 dark:text-white-light">CLI Based</h5>
                            <p class="text-white-dark">Etiam sed augue ac justo tincidunt posuere. Vivamus euismod eros, nec risus malesuada.</p>
                            <button type="button" class="btn btn-primary mt-6">Explore More</button>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code2')">
                    <highlight>
                        <pre>
&lt;!-- card 2 --&gt;
&lt;div class=&quot;max-w-[19rem] w-full bg-white shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none&quot;&gt;
  &lt;div class=&quot;py-7 px-6&quot;&gt;
    &lt;div class=&quot;-mt-7 mb-7 -mx-6 rounded-tl rounded-tr h-[215px] overflow-hidden&quot;&gt;
      &lt;img src=&quot;/assets/images/profile-28.jpeg&quot; alt=&quot;&quot; class=&quot;w-full h-full object-cover&quot; /&gt;
    &lt;/div&gt;
    &lt;h5 class=&quot;text-[#3b3f5c] text-xl font-semibold mb-4 dark:text-white-light&quot;&gt;CLI Based&lt;/h5&gt;
    &lt;p class=&quot;text-white-dark&quot;&gt;Etiam sed augue ac justo tincidunt posuere. Vivamus euismod eros, nec risus malesuada.&lt;/p&gt;
    &lt;button type=&quot;button&quot; class=&quot;btn btn-primary mt-6&quot;&gt;Explore More&lt;/button&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Card 3 -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Card 3</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code3')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5 flex items-center justify-center">
                    <div
                        class="max-w-[18rem] w-full bg-[#3b3f5c] shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none p-5"
                    >
                        <div class="text-center text-black-light">
                            <div class="mb-5 w-20 h-20 rounded-full overflow-hidden mx-auto">
                                <img src="/assets/images/profile-34.jpeg" alt="" class="w-full h-full object-cover" />
                            </div>
                            <h5 class="text-white text-[15px] font-semibold mb-2">Luke Ivory</h5>
                            <p>Manager</p>
                            <div class="flex justify-center items-center text-warning my-4">
                                <icon-star class="fill-warning" />
                                <icon-star class="fill-warning" />
                                <icon-star class="fill-warning" />
                                <icon-star class="fill-warning" />
                                <icon-star />
                            </div>
                            <p class="font-semibold italic">
                                Maecenas nec mi vel lacus condimentum rhoncus dignissim egestas orci. Integer blandit porta placerat. Vestibulum in ultricies.
                            </p>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code3')">
                    <highlight>
                        <pre>
&lt;!-- card 3 --&gt;
&lt;div class=&quot;max-w-[18rem] w-full bg-[#3b3f5c] shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none p-5&quot;&gt;
  &lt;div class=&quot;text-center text-black-light&quot;&gt;
    &lt;div class=&quot;mb-5 w-20 h-20 rounded-full overflow-hidden mx-auto&quot;&gt;
      &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-full h-full object-cover&quot; /&gt;
    &lt;/div&gt;
    &lt;h5 class=&quot;text-white text-[15px] font-semibold mb-2&quot;&gt;Luke Ivory&lt;/h5&gt;
    &lt;p&gt;Manager&lt;/p&gt;
    &lt;div class=&quot;flex justify-center items-center text-[#e2a03f] my-4&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/div&gt;
    &lt;p class=&quot;font-semibold italic&quot;&gt;Maecenas nec mi vel lacus condimentum rhoncus dignissim egestas orci. Integer blandit porta placerat. Vestibulum in ultricies.&lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Card 4 -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Card 4</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code4')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5 flex items-center justify-center">
                    <div
                        class="max-w-[30rem] w-full bg-white shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none"
                    >
                        <div class="p-5 flex items-center flex-col sm:flex-row">
                            <div class="mb-5 w-20 h-20 rounded-full overflow-hidden">
                                <img src="/assets/images/profile-34.jpeg" alt="" class="w-full h-full object-cover" />
                            </div>
                            <div class="flex-1 ltr:sm:pl-5 rtl:sm:pr-5 text-center sm:text-left">
                                <h5 class="text-[#3b3f5c] text-[15px] font-semibold mb-2 dark:text-white-light">Luke Ivory</h5>
                                <p class="mb-2 text-white-dark">Manager</p>
                                <span class="badge bg-primary rounded-full">4.5</span>
                                <p class="font-semibold text-white-dark mt-4 sm:mt-8">
                                    Maecenas nec mi vel lacus condimentum rhoncus dignissim egestas orci. Integer blandit porta placerat. Vestibulum in
                                    ultricies.
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code4')">
                    <highlight>
                        <pre>
&lt;!-- card 4 --&gt;
&lt;div class=&quot;max-w-[30rem] w-full bg-white shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none&quot;&gt;
  &lt;div class=&quot;p-5 flex items-center flex-col sm:flex-row&quot;&gt;
    &lt;div class=&quot;mb-5 w-20 h-20 rounded-full overflow-hidden&quot;&gt;
      &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-full h-full object-cover&quot; /&gt;
    &lt;/div&gt;
    &lt;div class=&quot;flex-1 ltr:sm:pl-5 rtl:sm:pr-5 text-center sm:text-left&quot;&gt;
      &lt;h5 class=&quot;text-[#3b3f5c] text-[15px] font-semibold mb-2 dark:text-white-light&quot;&gt;Luke Ivory&lt;/h5&gt;
      &lt;p class=&quot;mb-2 text-white-dark&quot;&gt;Manager&lt;/p&gt;
      &lt;span class=&quot;badge bg-primary rounded-full&quot;&gt;4.5&lt;/span&gt;
      &lt;p class=&quot;font-semibold text-white-dark mt-4 sm:mt-8&quot;&gt;Maecenas nec mi vel lacus condimentum rhoncus dignissim egestas orci. Integer blandit porta placerat. Vestibulum in ultricies.&lt;/p&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Card 5 -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Card 5</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code5')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5 flex items-center justify-center">
                    <div
                        class="max-w-[20rem] w-full bg-secondary shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-0 dark:bg-secondary-dark-light dark:shadow-none p-5"
                    >
                        <div class="text-black-light">
                            <p class="font-semibold mb-5">
                                Maecenas nec mi vel lacus condimentum rhoncus dignissim egestas orci. Integer blandit porta placerat. Vestibulum in ultricies.
                            </p>
                            <div class="flex">
                                <div class="mb-5 w-14 h-14 rounded-full overflow-hidden mx-auto">
                                    <img src="/assets/images/profile-34.jpeg" alt="" class="w-full h-full object-cover" />
                                </div>
                                <div class="flex-1 ltr:pl-4 rtl:pr-4">
                                    <h5 class="text-white text-[15px] font-semibold mb-1">Luke Ivory</h5>
                                    <p>Manager</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code5')">
                    <highlight>
                        <pre>
&lt;!-- card 5 --&gt;
&lt;div class=&quot;max-w-[20rem] w-full bg-secondary shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-0 dark:bg-secondary-dark-light dark:shadow-none p-5&quot;&gt;
  &lt;div class=&quot;text-black-light&quot;&gt;
    &lt;p class=&quot;font-semibold mb-5&quot;&gt;Maecenas nec mi vel lacus condimentum rhoncus dignissim egestas orci. Integer blandit porta placerat. Vestibulum in ultricies.&lt;/p&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;div class=&quot;mb-5 w-14 h-14 rounded-full overflow-hidden mx-auto&quot;&gt;
        &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-full h-full object-cover&quot; /&gt;
      &lt;/div&gt;
      &lt;div class=&quot;flex-1 ltr:pl-4 rtl:pr-4&quot;&gt;
        &lt;h5 class=&quot;text-white text-[15px] font-semibold mb-1&quot;&gt;Luke Ivory&lt;/h5&gt;
        &lt;p&gt;Manager&lt;/p&gt;
      &lt;/div&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- Card 6 -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Card 6</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code6')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5 flex items-center justify-center">
                    <div
                        class="max-w-[20rem] w-full bg-white shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none p-5"
                    >
                        <div class="text-[#515365] dark:text-white-light">
                            <p class="font-semibold italic mb-5">
                                Maecenas nec mi vel lacus condimentum rhoncus dignissim egestas orci. Integer blandit porta placerat. Vestibulum in ultricies.
                            </p>
                            <div class="flex">
                                <div class="flex-1">
                                    <h5 class="text-[#3b3f5c] text-[15px] font-bold mb-1.5 dark:text-white-light">Luke Ivory</h5>
                                    <p class="text-white-dark mb-1.5">Manager</p>
                                    <div class="flex justify-start items-center text-[#e2a03f]">
                                        <icon-star class="w-3 h-3 fill-warning" />
                                        <icon-star class="w-3 h-3 fill-warning" />
                                        <icon-star class="w-3 h-3 fill-warning" />
                                        <icon-star class="w-3 h-3 fill-warning" />
                                        <icon-star class="w-3 h-3" />
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code6')">
                    <highlight>
                        <pre>
&lt;!-- card 6 --&gt;
&lt;div class=&quot;max-w-[20rem] w-full bg-white shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none p-5&quot;&gt;
  &lt;div class=&quot;text-[#515365] dark:text-white-light&quot;&gt;
    &lt;p class=&quot;font-semibold italic mb-5&quot;&gt;Maecenas nec mi vel lacus condimentum rhoncus dignissim egestas orci. Integer blandit porta placerat. Vestibulum in ultricies.&lt;/p&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;div class=&quot;flex-1&quot;&gt;
        &lt;h5 class=&quot;text-[#3b3f5c] text-[15px] font-bold mb-1.5 dark:text-white-light&quot;&gt;Luke Ivory&lt;/h5&gt;
        &lt;p class=&quot;text-white-dark mb-1.5&quot;&gt;Manager&lt;/p&gt;
        &lt;div class=&quot;flex justify-start items-center text-[#e2a03f]&quot;&gt;
          &lt;svg&gt; ... &lt;/svg&gt;
          &lt;svg&gt; ... &lt;/svg&gt;
          &lt;svg&gt; ... &lt;/svg&gt;
          &lt;svg&gt; ... &lt;/svg&gt;
          &lt;svg&gt; ... &lt;/svg&gt;
        &lt;/div&gt;
      &lt;/div&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Card 7 -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Card 7</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code7')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5 flex items-center justify-center">
                    <div
                        class="max-w-[20rem] w-full bg-primary shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-0 dark:bg-primary-dark-light dark:shadow-none p-5"
                    >
                        <div class="text-center font-semibold">
                            <h5 class="text-white text-xl font-bold mb-5 dark:text-white-light">Rating</h5>
                            <p class="text-white mb-5 text-base">(4.3)</p>
                            <div class="flex justify-center items-center gap-1 text-[#e2a03f]">
                                <icon-star class="w-4.5 h-4.5 fill-warning" />
                                <icon-star class="w-4.5 h-4.5 fill-warning" />
                                <icon-star class="w-4.5 h-4.5 fill-warning" />
                                <icon-star class="w-4.5 h-4.5 fill-warning" />
                                <icon-star class="w-4.5 h-4.5" />
                                <span class="text-white ltr:ml-1 rtl:mr-1">(94)</span>
                            </div>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code7')">
                    <highlight>
                        <pre>
&lt;!-- card 7 --&gt;
&lt;div class=&quot;max-w-[20rem] w-full bg-primary shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-0 dark:bg-primary-dark-light dark:shadow-none p-5&quot;&gt;
  &lt;div class=&quot;text-center font-semibold&quot;&gt;
    &lt;h5 class=&quot;text-white text-xl font-bold mb-5 dark:text-white-light&quot;&gt;Rating&lt;/h5&gt;
    &lt;p class=&quot;text-white mb-5 text-base&quot;&gt;(4.3)&lt;/p&gt;
    &lt;div class=&quot;flex justify-center items-center gap-1 text-[#e2a03f]&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      &lt;span class=&quot;text-white ltr:ml-1 rtl:mr-1&quot;&gt;(94)&lt;/span&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Card 8 -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Card 8</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code8')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5 flex items-center justify-center">
                    <div
                        class="max-w-[24rem] w-full bg-white shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none p-5"
                    >
                        <div class="flex justify-between mb-5">
                            <h6 class="text-[#0e1726] font-semibold text-base dark:text-white-light">Placed Order</h6>
                            <span class="badge bg-primary/10 text-primary py-1.5 dark:bg-primary dark:text-white">IN PROGRESS</span>
                        </div>
                        <div class="flex items-center justify-start -space-x-3 rtl:space-x-reverse mb-5">
                            <img
                                class="w-9 h-9 rounded-full overflow-hidden object-cover ring-2 ring-white dark:ring-[#515365] shadow-[0_0_15px_1px_rgba(113,106,202,0.30)] dark:shadow-none"
                                src="/assets/images/profile-34.jpeg"
                                alt=""
                            />
                            <img
                                class="w-9 h-9 rounded-full overflow-hidden object-cover ring-2 ring-white dark:ring-[#515365] shadow-[0_0_15px_1px_rgba(113,106,202,0.30)] dark:shadow-none"
                                src="/assets/images/profile-34.jpeg"
                                alt=""
                            />
                            <img
                                class="w-9 h-9 rounded-full overflow-hidden object-cover ring-2 ring-white dark:ring-[#515365] shadow-[0_0_15px_1px_rgba(113,106,202,0.30)] dark:shadow-none"
                                src="/assets/images/profile-34.jpeg"
                                alt=""
                            />
                            <span
                                class="bg-white rounded-full px-2 py-1 text-primary text-xs shadow-[0_0_20px_0_#d0d0d0] dark:shadow-none dark:bg-[#0e1726] dark:text-white"
                                >+5 more</span
                            >
                        </div>
                        <div class="text-right">
                            <span class="text-primary font-semibold">60%</span>
                            <div class="bg-[#ebedf2] dark:bg-[#0e1726] rounded-full w-full h-1.5 mt-1.5">
                                <div class="rounded-full bg-primary h-full" style="width: 60%"></div>
                            </div>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code8')">
                    <highlight>
                        <pre>
&lt;!-- card 8 --&gt;
&lt;div class=&quot;max-w-[24rem] w-full bg-white shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none p-5&quot;&gt;
  &lt;div class=&quot;flex justify-between mb-5&quot;&gt;
    &lt;h6 class=&quot;text-[#0e1726] font-semibold text-base dark:text-white-light&quot;&gt;Placed Order&lt;/h6&gt;
    &lt;span class=&quot;badge bg-primary/10 text-primary py-1.5 dark:bg-primary dark:text-white&quot;&gt;IN PROGRESS&lt;/span&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex items-center justify-start -space-x-3 rtl:space-x-reverse mb-5&quot;&gt;
    &lt;img
      class=&quot;w-9 h-9 rounded-full overflow-hidden object-cover ring-2 ring-white dark:ring-[#515365] shadow-[0_0_15px_1px_rgba(113,106,202,0.30)] dark:shadow-none&quot;
      src=&quot;/assets/images/profile-34.jpeg&quot;
      alt=&quot;&quot;
    /&gt;
    &lt;img
      class=&quot;w-9 h-9 rounded-full overflow-hidden object-cover ring-2 ring-white dark:ring-[#515365] shadow-[0_0_15px_1px_rgba(113,106,202,0.30)] dark:shadow-none&quot;
      src=&quot;/assets/images/profile-34.jpeg&quot;
      alt=&quot;&quot;
    /&gt;
    &lt;img
      class=&quot;w-9 h-9 rounded-full overflow-hidden object-cover ring-2 ring-white dark:ring-[#515365] shadow-[0_0_15px_1px_rgba(113,106,202,0.30)] dark:shadow-none&quot;
      src=&quot;/assets/images/profile-34.jpeg&quot;
      alt=&quot;&quot;
    /&gt;
    &lt;span class=&quot;bg-white rounded-full px-2 py-1 text-primary text-xs shadow-[0_0_20px_0_#d0d0d0] dark:shadow-none dark:bg-[#0e1726] dark:text-white&quot;&gt;+5 more&lt;/span&gt;
  &lt;/div&gt;
  &lt;div class=&quot;text-right&quot;&gt;
    &lt;span class=&quot;text-primary font-semibold&quot;&gt;60%&lt;/span&gt;
    &lt;div class=&quot;bg-[#ebedf2] dark:bg-[#0e1726] rounded-full w-full h-1.5 mt-1.5&quot;&gt;
      &lt;div class=&quot;rounded-full bg-primary h-full&quot; style=&quot;width: 60%&quot;&gt;&lt;/div&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Card 9 -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Card 9</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code9')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5 flex items-center justify-center">
                    <div
                        class="max-w-[22rem] w-full bg-white shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none"
                    >
                        <div class="py-7 px-6">
                            <div class="-mt-7 mb-7 -mx-6 rounded-tl rounded-tr h-[260px] overflow-hidden">
                                <img src="/assets/images/profile-28.jpeg" alt="" class="w-full h-full object-cover" />
                            </div>
                            <p class="text-primary text-xs mb-1.5 font-bold">25 Sep 2020</p>
                            <h5 class="text-[#3b3f5c] text-[15px] font-bold mb-4 dark:text-white-light">How to Start a Blog in 5 Easy Steps.</h5>
                            <p class="text-white-dark">Vestibulum vestibulum tortor ut eros tincidunt, ut rutrum elit volutpat.</p>
                            <div
                                class="relative flex justify-between mt-6 pt-4 before:w-[250px] before:h-[1px] before:bg-[#e0e6ed] before:inset-x-0 before:top-0 before:absolute before:mx-auto dark:before:bg-[#1b2e4b]"
                            >
                                <div class="flex items-center font-semibold">
                                    <div class="w-9 h-9 rounded-full overflow-hidden inline-block ltr:mr-2 rtl:ml-2.5 shrink-0">
                                        <span class="flex w-full h-full items-center justify-center bg-[#515365] text-[#e0e6ed]">AG</span>
                                    </div>
                                    <div class="text-[#515365] dark:text-white-dark">Luke Ivory</div>
                                </div>
                                <div class="flex font-semibold">
                                    <div class="text-primary flex items-center ltr:mr-3 rtl:ml-3">
                                        <icon-heart class="w-4 h-4 ltr:mr-1 rtl:ml-1" />
                                        51
                                    </div>
                                    <div class="text-primary flex items-center">
                                        <icon-eye class="w-4 h-4 ltr:mr-1 rtl:ml-1" />
                                        250
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code9')">
                    <highlight>
                        <pre>
&lt;!-- card 9 --&gt;
&lt;div class=&quot;max-w-[22rem] w-full bg-white shadow-[4px_6px_10px_-3px_#bfc9d4] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] dark:bg-[#191e3a] dark:shadow-none&quot;&gt;
  &lt;div class=&quot;py-7 px-6&quot;&gt;
    &lt;div class=&quot;-mt-7 mb-7 -mx-6 rounded-tl rounded-tr h-[260px] overflow-hidden&quot;&gt;
      &lt;img src=&quot;/assets/images/profile-28.jpeg&quot; alt=&quot;&quot; class=&quot;w-full h-full object-cover&quot; /&gt;
    &lt;/div&gt;
    &lt;p class=&quot;text-primary text-xs mb-1.5 font-bold&quot;&gt;25 Sep 2020&lt;/p&gt;
    &lt;h5 class=&quot;text-[#3b3f5c] text-[15px] font-bold mb-4 dark:text-white-light&quot;&gt;How to Start a Blog in 5 Easy Steps.&lt;/h5&gt;
    &lt;p class=&quot;text-white-dark&quot;&gt;Vestibulum vestibulum tortor ut eros tincidunt, ut rutrum elit volutpat.&lt;/p&gt;
    &lt;div
      class=&quot;
        relative
        flex
        justify-between
        mt-6
        pt-4
        before:w-[250px] before:h-[1px] before:bg-[#e0e6ed] before:inset-x-0 before:top-0 before:absolute before:mx-auto
        dark:before:bg-[#1b2e4b]
      &quot;
    &gt;
      &lt;div class=&quot;flex items-center font-semibold&quot;&gt;
        &lt;div class=&quot;w-9 h-9 rounded-full overflow-hidden inline-block ltr:mr-2 rtl:ml-2.5&quot;&gt;
          &lt;span class=&quot;flex w-full h-full items-center justify-center bg-[#515365] text-[#e0e6ed]&quot;&gt;AG&lt;/span&gt;
        &lt;/div&gt;
        &lt;div class=&quot;text-[#515365] dark:text-white-dark&quot;&gt;Luke Ivory&lt;/div&gt;
      &lt;/div&gt;
      &lt;div class=&quot;flex font-semibold&quot;&gt;
        &lt;div class=&quot;text-primary flex items-center ltr:mr-3 rtl:ml-3&quot;&gt;
          &lt;svg&gt; ... &lt;/svg&gt;
          51
        &lt;/div&gt;
        &lt;div class=&quot;text-primary flex items-center&quot;&gt;
          &lt;svg&gt; ... &lt;/svg&gt;
          250
        &lt;/div&gt;
      &lt;/div&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
        </div>
    </div>
</template>
<script lang="ts" setup>
    import highlight from '@/components/plugins/highlight.vue';
    import codePreview from '@/composables/codePreview';
    import { useMeta } from '@/composables/use-meta';

    import IconCode from '@/components/icon/icon-code.vue';
    import IconDroplet from '@/components/icon/icon-droplet.vue';
    import IconStar from '@/components/icon/icon-star.vue';
    import IconHeart from '@/components/icon/icon-heart.vue';
    import IconEye from '@/components/icon/icon-eye.vue';

    useMeta({ title: 'Cards' });

    const { codeArr, toggleCode } = codePreview();
</script>
