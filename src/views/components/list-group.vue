<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Components</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>List Group</span>
            </li>
        </ul>
        <div class="pt-5 grid grid-cols-1 lg:grid-cols-2 gap-6">
            <!-- Basic -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Basic</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code1')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex flex-col rounded-md border border-[#e0e6ed] dark:border-[#1b2e4b]">
                        <div class="border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5">Cras justo odio</div>
                        <div class="border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5">Dapibus ac facilisis in</div>
                        <div
                            class="border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 bg-primary text-white shadow-[0_1px_15px_1px_rgba(67,97,238,0.15)]"
                        >
                            Morbi leo risus
                        </div>
                        <div class="border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5">Porta ac consectetur ac</div>
                        <div class="px-4 py-2.5">Vestibulum at eros</div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code1')">
                    <highlight>
                        <pre>
&lt;!-- basic --&gt;
&lt;div class=&quot;flex flex-col rounded-md border border-[#e0e6ed] dark:border-[#1b2e4b]&quot;&gt;
  &lt;div class=&quot;border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5&quot;&gt;Cras justo odio&lt;/div&gt;
  &lt;div class=&quot;border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5&quot;&gt;Dapibus ac facilisis in&lt;/div&gt;
  &lt;div class=&quot;border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 bg-primary text-white shadow-[0_1px_15px_1px_rgba(67,97,238,0.15)]&quot;&gt;Morbi leo risus&lt;/div&gt;
  &lt;div class=&quot;border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5&quot;&gt;Porta ac consectetur ac&lt;/div&gt;
  &lt;div class=&quot;px-4 py-2.5&quot;&gt;Vestibulum at eros&lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Links -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Links</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code2')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex flex-col rounded-md border border-[#e0e6ed] dark:border-[#1b2e4b]">
                        <a href="javascript:;" class="border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10"
                            >Cras justo odio</a
                        >
                        <a href="javascript:;" class="border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10"
                            >Dapibus ac facilisis in</a
                        >
                        <a
                            href="javascript:;"
                            class="border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 bg-primary text-white shadow-[0_1px_15px_1px_rgba(67,97,238,0.15)] hover:bg-[#eee] dark:hover:bg-[#eee]/10 hover:text-black dark:hover:text-white"
                            >Morbi leo risus</a
                        >
                        <a href="javascript:;" class="border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10"
                            >Porta ac consectetur ac</a
                        >
                        <a href="javascript:;" class="px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10">Vestibulum at eros</a>
                    </div>
                </div>
                <template v-if="codeArr.includes('code2')">
                    <highlight>
                        <pre>
&lt;!-- links --&gt;
&lt;div class=&quot;flex flex-col rounded-md border border-[#e0e6ed] dark:border-[#1b2e4b]&quot;&gt;
  &lt;a href=&quot;javascript:;&quot; class=&quot;border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10&quot;&gt;Cras justo odio&lt;/a&gt;
  &lt;a href=&quot;javascript:;&quot; class=&quot;border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10&quot;&gt;Dapibus ac facilisis in&lt;/a&gt;
  &lt;a
    href=&quot;javascript:;&quot;
    class=&quot;
      border-b border-[#e0e6ed]
      dark:border-[#1b2e4b]
      px-4
      py-2.5
      bg-primary
      text-white
      shadow-[0_1px_15px_1px_rgba(67,97,238,0.15)]
      hover:bg-[#eee]
      dark:hover:bg-[#eee]/10
      hover:text-black
      dark:hover:text-white
    &quot;
    &gt;Morbi leo risus&lt;/a
  &gt;
  &lt;a href=&quot;javascript:;&quot; class=&quot;border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10&quot;&gt;Porta ac consectetur ac&lt;/a&gt;
  &lt;a href=&quot;javascript:;&quot; class=&quot;px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10&quot;&gt;Vestibulum at eros&lt;/a&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Icons -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Icons</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code3')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex flex-col rounded-md border border-[#e0e6ed] dark:border-[#1b2e4b]">
                        <div class="flex border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10">
                            <div class="ltr:mr-2 rtl:ml-2.5 mt-0.5 text-primary">
                                <icon-mail class="w-5 h-5" />
                            </div>
                            <div class="flex-1 font-semibold">
                                <h6 class="mb-1 text-base">Messages</h6>
                                <p class="text-xs">4 New Messages</p>
                            </div>
                        </div>
                        <div
                            class="flex border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 bg-primary text-white shadow-[0_1px_15px_1px_rgba(67,97,238,0.15)] hover:bg-[#eee] dark:hover:bg-[#eee]/10 hover:text-black dark:hover:text-white group"
                        >
                            <div class="ltr:mr-2 rtl:ml-2.5 mt-0.5 text-white group-hover:text-primary">
                                <icon-map-pin />
                            </div>
                            <div class="flex-1 font-semibold">
                                <h6 class="mb-1 text-base">Locations</h6>
                                <p class="text-xs">25 New Travel Locations</p>
                            </div>
                        </div>
                        <div class="flex px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10">
                            <div class="ltr:mr-2 rtl:ml-2.5 mt-0.5 text-primary">
                                <icon-droplet />
                            </div>
                            <div class="flex-1 font-semibold">
                                <h6 class="mb-1 text-base">Flexible</h6>
                                <p class="text-xs">Customization Flexibility</p>
                            </div>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code3')">
                    <highlight>
                        <pre>
&lt;!-- icons --&gt;
&lt;div class=&quot;flex flex-col rounded-md border border-[#e0e6ed] dark:border-[#1b2e4b]&quot;&gt;
  &lt;div class=&quot;flex border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10&quot;&gt;
    &lt;div class=&quot;ltr:mr-2 rtl:ml-2.5 mt-0.5 text-primary&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/div&gt;
    &lt;div class=&quot;flex-1 font-semibold&quot;&gt;
      &lt;h6 class=&quot;mb-1 text-base&quot;&gt;Messages&lt;/h6&gt;
      &lt;p class=&quot;text-xs&quot;&gt;4 New Messages&lt;/p&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div
    class=&quot;
      flex
      border-b border-[#e0e6ed]
      dark:border-[#1b2e4b]
      px-4
      py-2.5
      bg-primary
      text-white
      shadow-[0_1px_15px_1px_rgba(67,97,238,0.15)]
      hover:bg-[#eee]
      dark:hover:bg-[#eee]/10
      hover:text-black
      dark:hover:text-white
      group
    &quot;
  &gt;
    &lt;div class=&quot;ltr:mr-2 rtl:ml-2.5 mt-0.5 text-white group-hover:text-primary&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/div&gt;
    &lt;div class=&quot;flex-1 font-semibold&quot;&gt;
      &lt;h6 class=&quot;mb-1 text-base&quot;&gt;Locations&lt;/h6&gt;
      &lt;p class=&quot;text-xs&quot;&gt;25 New Travel Locations&lt;/p&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10&quot;&gt;
    &lt;div class=&quot;ltr:mr-2 rtl:ml-2.5 mt-0.5 text-primary&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/div&gt;
    &lt;div class=&quot;flex-1 font-semibold&quot;&gt;
      &lt;h6 class=&quot;mb-1 text-base&quot;&gt;Flexible&lt;/h6&gt;
      &lt;p class=&quot;text-xs&quot;&gt;Customization Flexibility&lt;/p&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Images -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Images</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code4')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex flex-col rounded-md border border-[#e0e6ed] dark:border-[#1b2e4b]">
                        <div class="flex border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10">
                            <div class="ltr:mr-3 rtl:ml-3">
                                <img src="/assets/images/profile-1.jpeg" alt="" class="rounded-full w-12 h-12 object-cover" />
                            </div>
                            <div class="flex-1 font-semibold">
                                <h6 class="mb-1 text-base">Luke Ivory</h6>
                                <p class="text-xs">Project Lead</p>
                            </div>
                        </div>
                        <div
                            class="flex border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 bg-primary text-white shadow-[0_1px_15px_1px_rgba(67,97,238,0.15)] hover:bg-[#eee] dark:hover:bg-[#eee]/10 hover:text-black dark:hover:text-white group"
                        >
                            <div class="ltr:mr-3 rtl:ml-3">
                                <img src="/assets/images/profile-2.jpeg" alt="" class="rounded-full w-12 h-12 object-cover" />
                            </div>
                            <div class="flex-1 font-semibold">
                                <h6 class="mb-1 text-base">Sonia Shaw</h6>
                                <p class="text-xs">Web Designer</p>
                            </div>
                        </div>
                        <div class="flex px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10">
                            <div class="ltr:mr-3 rtl:ml-3">
                                <img src="/assets/images/profile-3.jpeg" alt="" class="rounded-full w-12 h-12 object-cover" />
                            </div>
                            <div class="flex-1 font-semibold">
                                <h6 class="mb-1 text-base">Dale Butler</h6>
                                <p class="text-xs">Developer</p>
                            </div>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code4')">
                    <highlight>
                        <pre>
&lt;!-- images --&gt;
&lt;div class=&quot;flex flex-col rounded-md border border-[#e0e6ed] dark:border-[#1b2e4b]&quot;&gt;
  &lt;div class=&quot;flex border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10&quot;&gt;
    &lt;div class=&quot;ltr:mr-3 rtl:ml-3&quot;&gt;
      &lt;img src=&quot;/assets/images/profile-1.jpeg&quot; alt=&quot;&quot; class=&quot;rounded-full w-12 h-12 object-cover&quot; /&gt;
    &lt;/div&gt;
    &lt;div class=&quot;flex-1 font-semibold&quot;&gt;
      &lt;h6 class=&quot;mb-1 text-base&quot;&gt;Luke Ivory&lt;/h6&gt;
      &lt;p class=&quot;text-xs&quot;&gt;Project Lead&lt;/p&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div
    class=&quot;
      flex
      border-b border-[#e0e6ed]
      dark:border-[#1b2e4b]
      px-4
      py-2.5
      bg-primary
      text-white
      shadow-[0_1px_15px_1px_rgba(67,97,238,0.15)]
      hover:bg-[#eee]
      dark:hover:bg-[#eee]/10
      hover:text-black
      dark:hover:text-white
      group
    &quot;
  &gt;
    &lt;div class=&quot;ltr:mr-3 rtl:ml-3&quot;&gt;
      &lt;img src=&quot;/assets/images/profile-2.jpeg&quot; alt=&quot;&quot; class=&quot;rounded-full w-12 h-12 object-cover&quot; /&gt;
    &lt;/div&gt;
    &lt;div class=&quot;flex-1 font-semibold&quot;&gt;
      &lt;h6 class=&quot;mb-1 text-base&quot;&gt;Sonia Shaw&lt;/h6&gt;
      &lt;p class=&quot;text-xs&quot;&gt;Web Designer&lt;/p&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10&quot;&gt;
    &lt;div class=&quot;ltr:mr-3 rtl:ml-3&quot;&gt;
      &lt;img src=&quot;/assets/images/profile-3.jpeg&quot; alt=&quot;&quot; class=&quot;rounded-full w-12 h-12 object-cover&quot; /&gt;
    &lt;/div&gt;
    &lt;div class=&quot;flex-1 font-semibold&quot;&gt;
      &lt;h6 class=&quot;mb-1 text-base&quot;&gt;Dale Butler&lt;/h6&gt;
      &lt;p class=&quot;text-xs&quot;&gt;Developer&lt;/p&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Task -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Task</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code5')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex flex-col rounded-md border border-[#e0e6ed] dark:border-[#1b2e4b]">
                        <div
                            class="flex space-x-4 rtl:space-x-reverse border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10"
                        >
                            <input id="tack_checkbox1" type="checkbox" class="form-checkbox" />
                            <label for="tack_checkbox1" class="mb-0 cursor-pointer"
                                >List groups are a flexible and powerful component for displaying simple.
                                <span class="badge bg-secondary my-auto ltr:ml-3 rtl:mr-3 hover:top-0">Project</span></label
                            >
                        </div>
                        <div
                            class="flex space-x-4 rtl:space-x-reverse border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 bg-primary text-white shadow-[0_1px_15px_1px_rgba(67,97,238,0.15)] hover:bg-[#eee] dark:hover:bg-[#eee]/10 hover:text-black dark:hover:text-white group"
                        >
                            <input id="tack_checkbox2" type="checkbox" class="form-checkbox checked:border-white-light dark:checked:border-[#253b5c]" />
                            <label for="tack_checkbox2" class="mb-0 cursor-pointer"
                                >List groups are a flexible and powerful component for displaying simple.
                                <span class="badge bg-info my-auto ltr:ml-3 rtl:mr-3 hover:top-0">Urgent</span></label
                            >
                        </div>
                        <div class="flex space-x-4 rtl:space-x-reverse px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10">
                            <input id="tack_checkbox3" type="checkbox" class="form-checkbox" />
                            <label for="tack_checkbox3" class="mb-0 cursor-pointer"
                                >List groups are a flexible and powerful component for displaying simple.
                                <span class="badge bg-success my-auto ltr:ml-3 rtl:mr-3 hover:top-0">Success</span></label
                            >
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code5')">
                    <highlight>
                        <pre>
&lt;!-- task --&gt;
&lt;div class=&quot;flex flex-col rounded-md border border-[#e0e6ed] dark:border-[#1b2e4b]&quot;&gt;
  &lt;div class=&quot;flex space-x-4 rtl:space-x-reverse border-b border-[#e0e6ed] dark:border-[#1b2e4b] px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10&quot;&gt;
    &lt;input id=&quot;tack_checkbox1&quot; type=&quot;checkbox&quot; class=&quot;form-checkbox&quot; /&gt;
    &lt;label for=&quot;tack_checkbox1&quot; class=&quot;mb-0 cursor-pointer&quot;
      &gt;List groups are a flexible and powerful component for displaying simple. &lt;span class=&quot;badge bg-secondary my-auto ltr:ml-3 rtl:mr-3 hover:top-0&quot;&gt;Project&lt;/span&gt;&lt;/label
    &gt;
  &lt;/div&gt;
  &lt;div
    class=&quot;
      flex
      space-x-4
      rtl:space-x-reverse
      border-b border-[#e0e6ed]
      dark:border-[#1b2e4b]
      px-4
      py-2.5
      bg-primary
      text-white
      shadow-[0_1px_15px_1px_rgba(67,97,238,0.15)]
      hover:bg-[#eee]
      dark:hover:bg-[#eee]/10
      hover:text-black
      dark:hover:text-white
      group
    &quot;
  &gt;
    &lt;input id=&quot;tack_checkbox2&quot; type=&quot;checkbox&quot; class=&quot;form-checkbox checked:border-white-light dark:checked:border-[#253b5c]&quot; /&gt;
    &lt;label for=&quot;tack_checkbox2&quot; class=&quot;mb-0 cursor-pointer&quot;
      &gt;List groups are a flexible and powerful component for displaying simple. &lt;span class=&quot;badge bg-info my-auto ltr:ml-3 rtl:mr-3 hover:top-0&quot;&gt;Urgent&lt;/span&gt;&lt;/label
    &gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex space-x-4 rtl:space-x-reverse px-4 py-2.5 hover:bg-[#eee] dark:hover:bg-[#eee]/10&quot;&gt;
    &lt;input id=&quot;tack_checkbox3&quot; type=&quot;checkbox&quot; class=&quot;form-checkbox&quot; /&gt;
    &lt;label for=&quot;tack_checkbox3&quot; class=&quot;mb-0 cursor-pointer&quot;
      &gt;List groups are a flexible and powerful component for displaying simple. &lt;span class=&quot;badge bg-success my-auto ltr:ml-3 rtl:mr-3 hover:top-0&quot;&gt;Success&lt;/span&gt;&lt;/label
    &gt;
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
    import IconMail from '@/components/icon/icon-mail.vue';
    import IconMapPin from '@/components/icon/icon-map-pin.vue';
    import IconDroplet from '@/components/icon/icon-droplet.vue';

    useMeta({ title: 'List Group' });
    const { codeArr, toggleCode } = codePreview();
</script>
