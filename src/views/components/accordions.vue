<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Components</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Accordians</span>
            </li>
        </ul>
        <div class="pt-5 space-y-8">
            <div class="panel p-3 flex items-center text-primary overflow-x-auto whitespace-nowrap">
                <div class="ring-2 ring-primary/30 rounded-full bg-primary text-white p-1.5 ltr:mr-3 rtl:ml-3">
                    <icon-bell />
                </div>
                <span class="ltr:mr-3 rtl:ml-3">Documentation: </span
                ><a href="https://www.npmjs.com/package/vue-height-collapsible" target="_blank" class="block hover:underline"
                    >https://www.npmjs.com/package/vue-height-collapsible</a
                >
            </div>
            <!-- basic -->
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Basic</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code1')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5">
                        <div class="space-y-2 font-semibold">
                            <div class="border border-[#d3d3d3] rounded dark:border-[#1b2e4b]">
                                <button
                                    type="button"
                                    class="p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]"
                                    :class="{ '!text-primary': accordians1 === 1 }"
                                    @click="accordians1 === 1 ? (accordians1 = null) : (accordians1 = 1)"
                                >
                                    Collapsible Group Item #1
                                    <div class="ltr:ml-auto rtl:mr-auto" :class="{ 'rotate-180': accordians1 === 1 }">
                                        <icon-caret-down />
                                    </div>
                                </button>
                                <vue-collapsible :isOpen="accordians1 === 1">
                                    <div class="space-y-2 p-4 text-white-dark text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]">
                                        <p>
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                        </p>
                                        <p>
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                        </p>
                                    </div>
                                </vue-collapsible>
                            </div>
                            <div class="border border-[#d3d3d3] dark:border-[#1b2e4b] rounded">
                                <button
                                    type="button"
                                    class="p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]"
                                    :class="{ '!text-primary': accordians1 === 2 }"
                                    @click="accordians1 === 2 ? (accordians1 = null) : (accordians1 = 2)"
                                >
                                    Collapsible Group Item #2
                                    <div class="ltr:ml-auto rtl:mr-auto" :class="{ 'rotate-180': accordians1 === 2 }">
                                        <icon-caret-down />
                                    </div>
                                </button>
                                <vue-collapsible :isOpen="accordians1 === 2">
                                    <div class="p-4 text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]">
                                        <ul class="space-y-1">
                                            <li><a href="javascript:;">Apple</a></li>
                                            <li><a href="javascript:;">Orange</a></li>
                                            <li><a href="javascript:;">Banana</a></li>
                                            <li><a href="javascript:;">list</a></li>
                                        </ul>
                                    </div>
                                </vue-collapsible>
                            </div>
                            <div class="border border-[#d3d3d3] dark:border-[#1b2e4b] rounded">
                                <button
                                    type="button"
                                    class="p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]"
                                    :class="{ '!text-primary': accordians1 === 3 }"
                                    @click="accordians1 === 3 ? (accordians1 = null) : (accordians1 = 3)"
                                >
                                    Collapsible Group Item #3
                                    <div class="ltr:ml-auto rtl:mr-auto" :class="{ 'rotate-180': accordians1 === 3 }">
                                        <icon-caret-down />
                                    </div>
                                </button>
                                <vue-collapsible :isOpen="accordians1 === 3">
                                    <div class="p-4 text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]">
                                        <p>
                                            Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia
                                            aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor,
                                            sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh
                                            helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo.
                                            Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them
                                            accusamus labore sustainable VHS.
                                        </p>
                                        <button type="button" class="btn btn-primary mt-4">Accept</button>
                                    </div>
                                </vue-collapsible>
                            </div>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code1')">
                        <highlight>
                            <pre>
&lt;!-- basic --&gt;
&lt;div class=&quot;space-y-2 font-semibold&quot;&gt;
  &lt;div class=&quot;border border-[#d3d3d3] rounded dark:border-[#1b2e4b]&quot;&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]&quot;
      :class=&quot;{ '!text-primary': accordians1 === 1 }&quot;
      @click=&quot;accordians1 === 1 ? (accordians1 = null) : (accordians1 = 1)&quot;
    &gt;
      Collapsible Group Item #1
      &lt;div class=&quot;ltr:ml-auto rtl:mr-auto&quot; :class=&quot;{ 'rotate-180': accordians1 === 1 }&quot;&gt;
        &lt;svg&gt; ... &lt;/svg&gt;
      &lt;/div&gt;
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;accordians1 === 1&quot;&gt;
      &lt;div class=&quot;space-y-2 p-4 text-white-dark text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]&quot;&gt;
        &lt;p&gt;
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
          ullamco laboris nisi ut aliquip ex ea commodo consequat.
        &lt;/p&gt;
        &lt;p&gt;
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
          ullamco laboris nisi ut aliquip ex ea commodo consequat.
        &lt;/p&gt;
      &lt;/div&gt;
    &lt;/vue-collapsible&gt;
  &lt;/div&gt;
  &lt;div class=&quot;border border-[#d3d3d3] dark:border-[#1b2e4b] rounded&quot;&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]&quot;
      :class=&quot;{ '!text-primary': accordians1 === 2 }&quot;
      @click=&quot;accordians1 === 2 ? (accordians1 = null) : (accordians1 = 2)&quot;
    &gt;
      Collapsible Group Item #2
      &lt;div class=&quot;ltr:ml-auto rtl:mr-auto&quot; :class=&quot;{ 'rotate-180': accordians1 === 2 }&quot;&gt;
        &lt;svg&gt; ... &lt;/svg&gt;
      &lt;/div&gt;
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;accordians1 === 2&quot;&gt;
      &lt;div class=&quot;p-4 text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]&quot;&gt;
        &lt;ul class=&quot;space-y-1&quot;&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Apple&lt;/a&gt;&lt;/li&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Orange&lt;/a&gt;&lt;/li&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Banana&lt;/a&gt;&lt;/li&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;list&lt;/a&gt;&lt;/li&gt;
        &lt;/ul&gt;
      &lt;/div&gt;
    &lt;/vue-collapsible&gt;
  &lt;/div&gt;
  &lt;div class=&quot;border border-[#d3d3d3] dark:border-[#1b2e4b] rounded&quot;&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]&quot;
      :class=&quot;{ '!text-primary': accordians1 === 3 }&quot;
      @click=&quot;accordians1 === 3 ? (accordians1 = null) : (accordians1 = 3)&quot;
    &gt;
      Collapsible Group Item #3
      &lt;div class=&quot;ltr:ml-auto rtl:mr-auto&quot; :class=&quot;{ 'rotate-180': accordians1 === 3 }&quot;&gt;
        &lt;svg&gt; ... &lt;/svg&gt;
      &lt;/div&gt;
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;accordians1 === 3&quot;&gt;
      &lt;div class=&quot;p-4 text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]&quot;&gt;
        &lt;p&gt;
          Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa
          nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft
          beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt
          you probably haven't heard of them accusamus labore sustainable VHS.
        &lt;/p&gt;
        &lt;button type=&quot;button&quot; class=&quot;btn btn-primary mt-4&quot;&gt;Accept&lt;/button&gt;
      &lt;/div&gt;
    &lt;/vue-collapsible&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref } from 'vue';
import VueCollapsible from 'vue-height-collapsible/vue3';
const accordians1: any = ref(1);
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Without Spacing -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Without Spacing</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code2')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5">
                        <div class="border border-[#d3d3d3] dark:border-[#3b3f5c] rounded font-semibold">
                            <div class="border-b border-[#d3d3d3] dark:border-[#3b3f5c]">
                                <button
                                    type="button"
                                    class="p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]"
                                    :class="{ '!text-primary': accordians2 === 1 }"
                                    @click="accordians2 === 1 ? (accordians2 = null) : (accordians2 = 1)"
                                >
                                    Collapsible Group Item #1
                                    <div class="ltr:ml-auto rtl:mr-auto" :class="{ 'rotate-180': accordians2 === 1 }">
                                        <icon-caret-down />
                                    </div>
                                </button>
                                <vue-collapsible :isOpen="accordians2 === 1">
                                    <div class="space-y-2 p-4 text-white-dark text-[13px]">
                                        <p>
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                        </p>
                                        <p>
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                        </p>
                                    </div>
                                </vue-collapsible>
                            </div>

                            <div class="border-b border-[#d3d3d3] dark:border-[#3b3f5c]">
                                <button
                                    type="button"
                                    class="p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]"
                                    :class="{ '!text-primary': accordians2 === 2 }"
                                    @click="accordians2 === 2 ? (accordians2 = null) : (accordians2 = 2)"
                                >
                                    Collapsible Group Item #2
                                    <div class="ltr:ml-auto rtl:mr-auto" :class="{ 'rotate-180': accordians2 === 2 }">
                                        <icon-caret-down />
                                    </div>
                                </button>
                                <vue-collapsible :isOpen="accordians2 === 2">
                                    <div class="p-4 text-[13px]">
                                        <ul class="space-y-1">
                                            <li><a href="javascript:;">Apple</a></li>
                                            <li><a href="javascript:;">Orange</a></li>
                                            <li><a href="javascript:;">Banana</a></li>
                                            <li><a href="javascript:;">list</a></li>
                                        </ul>
                                    </div>
                                </vue-collapsible>
                            </div>

                            <div>
                                <button
                                    type="button"
                                    class="p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]"
                                    :class="{ '!text-primary': accordians2 === 3 }"
                                    @click="accordians2 === 3 ? (accordians2 = null) : (accordians2 = 3)"
                                >
                                    Collapsible Group Item #3
                                    <div class="ltr:ml-auto rtl:mr-auto" :class="{ 'rotate-180': accordians2 === 3 }">
                                        <icon-caret-down />
                                    </div>
                                </button>
                                <vue-collapsible :isOpen="accordians2 === 3">
                                    <div class="p-4 text-[13px]">
                                        <p>
                                            Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia
                                            aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor,
                                            sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh
                                            helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo.
                                            Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them
                                            accusamus labore sustainable VHS.
                                        </p>
                                        <button type="button" class="btn btn-primary mt-4">Accept</button>
                                    </div>
                                </vue-collapsible>
                            </div>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code2')">
                        <highlight>
                            <pre>
&lt;!-- without spacing --&gt;
&lt;div class=&quot;border border-[#d3d3d3] dark:border-[#3b3f5c] rounded font-semibold&quot;&gt;
  &lt;div class=&quot;border-b border-[#d3d3d3] dark:border-[#3b3f5c]&quot;&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]&quot;
      :class=&quot;{ '!text-primary': accordians2 === 1 }&quot;
      @click=&quot;accordians2 === 1 ? (accordians2 = null) : (accordians2 = 1)&quot;
    &gt;
      Collapsible Group Item #1
      &lt;div class=&quot;ltr:ml-auto rtl:mr-auto&quot; :class=&quot;{ 'rotate-180': accordians2 === 1 }&quot;&gt;
        &lt;svg&gt; ... &lt;/svg&gt;
      &lt;/div&gt;
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;accordians2 === 1&quot;&gt;
      &lt;div class=&quot;space-y-2 p-4 text-white-dark text-[13px]&quot;&gt;
        &lt;p&gt;
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
          ullamco laboris nisi ut aliquip ex ea commodo consequat.
        &lt;/p&gt;
        &lt;p&gt;
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
          ullamco laboris nisi ut aliquip ex ea commodo consequat.
        &lt;/p&gt;
      &lt;/div&gt;
    &lt;/vue-collapsible&gt;
  &lt;/div&gt;

  &lt;div class=&quot;border-b border-[#d3d3d3] dark:border-[#3b3f5c]&quot;&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]&quot;
      :class=&quot;{ '!text-primary': accordians2 === 2 }&quot;
      @click=&quot;accordians2 === 2 ? (accordians2 = null) : (accordians2 = 2)&quot;
    &gt;
      Collapsible Group Item #2
      &lt;div class=&quot;ltr:ml-auto rtl:mr-auto&quot; :class=&quot;{ 'rotate-180': accordians2 === 2 }&quot;&gt;
        &lt;svg&gt; ... &lt;/svg&gt;
      &lt;/div&gt;
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;accordians2 === 2&quot;&gt;
      &lt;div class=&quot;p-4 text-[13px]&quot;&gt;
        &lt;ul class=&quot;space-y-1&quot;&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Apple&lt;/a&gt;&lt;/li&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Orange&lt;/a&gt;&lt;/li&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Banana&lt;/a&gt;&lt;/li&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;list&lt;/a&gt;&lt;/li&gt;
        &lt;/ul&gt;
      &lt;/div&gt;
    &lt;/vue-collapsible&gt;
  &lt;/div&gt;

  &lt;div&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]&quot;
      :class=&quot;{ '!text-primary': accordians2 === 3 }&quot;
      @click=&quot;accordians2 === 3 ? (accordians2 = null) : (accordians2 = 3)&quot;
    &gt;
      Collapsible Group Item #3
      &lt;div class=&quot;ltr:ml-auto rtl:mr-auto&quot; :class=&quot;{ 'rotate-180': accordians2 === 3 }&quot;&gt;
        &lt;svg&gt; ... &lt;/svg&gt;
      &lt;/div&gt;
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;accordians2 === 3&quot;&gt;
      &lt;div class=&quot;p-4 text-[13px]&quot;&gt;
        &lt;p&gt;
          Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa
          nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft
          beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt
          you probably haven't heard of them accusamus labore sustainable VHS.
        &lt;/p&gt;
        &lt;button type=&quot;button&quot; class=&quot;btn btn-primary mt-4&quot;&gt;Accept&lt;/button&gt;
      &lt;/div&gt;
    &lt;/vue-collapsible&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref } from 'vue';
import VueCollapsible from 'vue-height-collapsible/vue3';
const accordians2: any = ref(1);
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Icons -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Icons</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code3')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5">
                        <div class="space-y-2 font-semibold">
                            <div class="border border-[#d3d3d3] dark:border-[#1b2e4b] rounded">
                                <button
                                    type="button"
                                    class="p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]"
                                    :class="{ '!text-primary': accordians3 === 1 }"
                                    @click="accordians3 === 1 ? (accordians3 = null) : (accordians3 = 1)"
                                >
                                    <icon-airplay class="ltr:mr-2 rtl:ml-2 text-primary shrink-0" />

                                    Collapsible Group Item #1
                                    <div class="ltr:ml-auto rtl:mr-auto" :class="{ 'rotate-180': accordians3 === 1 }">
                                        <icon-caret-down />
                                    </div>
                                </button>
                                <vue-collapsible :isOpen="accordians3 === 1">
                                    <div class="space-y-2 p-4 text-white-dark text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]">
                                        <p>
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                        </p>
                                        <p>
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                        </p>
                                    </div>
                                </vue-collapsible>
                            </div>

                            <div class="border border-[#d3d3d3] dark:border-[#1b2e4b] rounded">
                                <button
                                    type="button"
                                    class="p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]"
                                    :class="{ '!text-primary': accordians3 === 2 }"
                                    @click="accordians3 === 2 ? (accordians3 = null) : (accordians3 = 2)"
                                >
                                    <icon-box class="ltr:mr-2 rtl:ml-2 text-primary shrink-0" />

                                    Collapsible Group Item #2
                                    <div class="ltr:ml-auto rtl:mr-auto" :class="{ 'rotate-180': accordians3 === 2 }">
                                        <icon-caret-down />
                                    </div>
                                </button>
                                <vue-collapsible :isOpen="accordians3 === 2">
                                    <div class="p-4 text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]">
                                        <ul class="space-y-1">
                                            <li><a href="javascript:;">Apple</a></li>
                                            <li><a href="javascript:;">Orange</a></li>
                                            <li><a href="javascript:;">Banana</a></li>
                                            <li><a href="javascript:;">list</a></li>
                                        </ul>
                                    </div>
                                </vue-collapsible>
                            </div>

                            <div class="border border-[#d3d3d3] dark:border-[#1b2e4b] rounded">
                                <button
                                    type="button"
                                    class="p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]"
                                    :class="{ '!text-primary': accordians3 === 3 }"
                                    @click="accordians3 === 3 ? (accordians3 = null) : (accordians3 = 3)"
                                >
                                    <icon-layout class="ltr:mr-2 rtl:ml-2 text-primary shrink-0" />

                                    Collapsible Group Item #3
                                    <div class="ltr:ml-auto rtl:mr-auto" :class="{ 'rotate-180': accordians3 === 3 }">
                                        <icon-caret-down />
                                    </div>
                                </button>
                                <vue-collapsible :isOpen="accordians3 === 3">
                                    <div class="p-4 text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]">
                                        <p>
                                            Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia
                                            aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor,
                                            sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh
                                            helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo.
                                            Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them
                                            accusamus labore sustainable VHS.
                                        </p>
                                        <button type="button" class="btn btn-primary mt-4">Accept</button>
                                    </div>
                                </vue-collapsible>
                            </div>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code3')">
                        <highlight>
                            <pre>
&lt;!-- icons --&gt;
&lt;div class=&quot;space-y-2 font-semibold&quot;&gt;
  &lt;div class=&quot;border border-[#d3d3d3] dark:border-[#1b2e4b] rounded&quot;&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]&quot;
      :class=&quot;{ '!text-primary': accordians3 === 1 }&quot;
      @click=&quot;accordians3 === 1 ? (accordians3 = null) : (accordians3 = 1)&quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      Collapsible Group Item #1
      &lt;div class=&quot;ltr:ml-auto rtl:mr-auto&quot; :class=&quot;{ 'rotate-180': accordians3 === 1 }&quot;&gt;
        &lt;svg&gt; ... &lt;/svg&gt;
      &lt;/div&gt;
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;accordians3 === 1&quot;&gt;
      &lt;div class=&quot;space-y-2 p-4 text-white-dark text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]&quot;&gt;
        &lt;p&gt;
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
          ullamco laboris nisi ut aliquip ex ea commodo consequat.
        &lt;/p&gt;
        &lt;p&gt;
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
          ullamco laboris nisi ut aliquip ex ea commodo consequat.
        &lt;/p&gt;
      &lt;/div&gt;
    &lt;/vue-collapsible&gt;
  &lt;/div&gt;

  &lt;div class=&quot;border border-[#d3d3d3] dark:border-[#1b2e4b] rounded&quot;&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]&quot;
      :class=&quot;{ '!text-primary': accordians3 === 2 }&quot;
      @click=&quot;accordians3 === 2 ? (accordians3 = null) : (accordians3 = 2)&quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      Collapsible Group Item #2
      &lt;div class=&quot;ltr:ml-auto rtl:mr-auto&quot; :class=&quot;{ 'rotate-180': accordians3 === 2 }&quot;&gt;
        &lt;svg&gt; ... &lt;/svg&gt;
      &lt;/div&gt;
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;accordians3 === 2&quot;&gt;
      &lt;div class=&quot;p-4 text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]&quot;&gt;
        &lt;ul class=&quot;space-y-1&quot;&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Apple&lt;/a&gt;&lt;/li&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Orange&lt;/a&gt;&lt;/li&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Banana&lt;/a&gt;&lt;/li&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;list&lt;/a&gt;&lt;/li&gt;
        &lt;/ul&gt;
      &lt;/div&gt;
    &lt;/vue-collapsible&gt;
  &lt;/div&gt;

  &lt;div class=&quot;border border-[#d3d3d3] dark:border-[#1b2e4b] rounded&quot;&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]&quot;
      :class=&quot;{ '!text-primary': accordians3 === 3 }&quot;
      @click=&quot;accordians3 === 3 ? (accordians3 = null) : (accordians3 = 3)&quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      Collapsible Group Item #3
      &lt;div class=&quot;ltr:ml-auto rtl:mr-auto&quot; :class=&quot;{ 'rotate-180': accordians3 === 3 }&quot;&gt;
        &lt;svg&gt; ... &lt;/svg&gt;
      &lt;/div&gt;
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;accordians3 === 3&quot;&gt;
      &lt;div class=&quot;p-4 text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]&quot;&gt;
        &lt;p&gt;
          Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa
          nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft
          beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt
          you probably haven't heard of them accusamus labore sustainable VHS.
        &lt;/p&gt;
        &lt;button type=&quot;button&quot; class=&quot;btn btn-primary mt-4&quot;&gt;Accept&lt;/button&gt;
      &lt;/div&gt;
    &lt;/vue-collapsible&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref } from 'vue';
import VueCollapsible from 'vue-height-collapsible/vue3';
const accordians3: any = ref(1);
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- no icons -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">No Icons</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code4')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5">
                        <div class="space-y-2 font-semibold">
                            <div class="border border-[#d3d3d3] rounded dark:border-[#1b2e4b]">
                                <button
                                    type="button"
                                    class="p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]"
                                    :class="{ '!text-primary': accordians4 === 1 }"
                                    @click="accordians4 === 1 ? (accordians4 = null) : (accordians4 = 1)"
                                >
                                    Collapsible Group Item #1
                                </button>
                                <vue-collapsible :isOpen="accordians4 === 1">
                                    <div class="space-y-2 p-4 text-white-dark text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]">
                                        <p>
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                        </p>
                                        <p>
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                        </p>
                                    </div>
                                </vue-collapsible>
                            </div>

                            <div class="border border-[#d3d3d3] dark:border-[#1b2e4b] rounded">
                                <button
                                    type="button"
                                    class="p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]"
                                    :class="{ '!text-primary': accordians4 === 2 }"
                                    @click="accordians4 === 2 ? (accordians4 = null) : (accordians4 = 2)"
                                >
                                    Collapsible Group Item #2
                                </button>
                                <vue-collapsible :isOpen="accordians4 === 2">
                                    <div class="p-4 text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]">
                                        <ul class="space-y-1">
                                            <li><a href="javascript:;">Apple</a></li>
                                            <li><a href="javascript:;">Orange</a></li>
                                            <li><a href="javascript:;">Banana</a></li>
                                            <li><a href="javascript:;">list</a></li>
                                        </ul>
                                    </div>
                                </vue-collapsible>
                            </div>

                            <div class="border border-[#d3d3d3] dark:border-[#1b2e4b] rounded">
                                <button
                                    type="button"
                                    class="p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]"
                                    :class="{ '!text-primary': accordians4 === 3 }"
                                    @click="accordians4 === 3 ? (accordians4 = null) : (accordians4 = 3)"
                                >
                                    Collapsible Group Item #3
                                </button>
                                <vue-collapsible :isOpen="accordians4 === 3">
                                    <div class="p-4 text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]">
                                        <p>
                                            Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia
                                            aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor,
                                            sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh
                                            helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo.
                                            Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them
                                            accusamus labore sustainable VHS.
                                        </p>
                                        <button type="button" class="btn btn-primary mt-4">Accept</button>
                                    </div>
                                </vue-collapsible>
                            </div>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code4')">
                        <highlight>
                            <pre>
&lt;!-- no icon --&gt;
&lt;div class=&quot;space-y-2 font-semibold&quot;&gt;
  &lt;div class=&quot;border border-[#d3d3d3] rounded dark:border-[#1b2e4b]&quot;&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]&quot;
      :class=&quot;{ '!text-primary': accordians4 === 1 }&quot;
      @click=&quot;accordians4 === 1 ? (accordians4 = null) : (accordians4 = 1)&quot;
    &gt;
      Collapsible Group Item #1
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;accordians4 === 1&quot;&gt;
      &lt;div class=&quot;space-y-2 p-4 text-white-dark text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]&quot;&gt;
        &lt;p&gt;
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
          ullamco laboris nisi ut aliquip ex ea commodo consequat.
        &lt;/p&gt;
        &lt;p&gt;
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
          ullamco laboris nisi ut aliquip ex ea commodo consequat.
        &lt;/p&gt;
      &lt;/div&gt;
    &lt;/vue-collapsible&gt;
  &lt;/div&gt;

  &lt;div class=&quot;border border-[#d3d3d3] dark:border-[#1b2e4b] rounded&quot;&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]&quot;
      :class=&quot;{ '!text-primary': accordians4 === 2 }&quot;
      @click=&quot;accordians4 === 2 ? (accordians4 = null) : (accordians4 = 2)&quot;
    &gt;
      Collapsible Group Item #2
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;accordians4 === 2&quot;&gt;
      &lt;div class=&quot;p-4 text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]&quot;&gt;
        &lt;ul class=&quot;space-y-1&quot;&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Apple&lt;/a&gt;&lt;/li&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Orange&lt;/a&gt;&lt;/li&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Banana&lt;/a&gt;&lt;/li&gt;
          &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;list&lt;/a&gt;&lt;/li&gt;
        &lt;/ul&gt;
      &lt;/div&gt;
    &lt;/vue-collapsible&gt;
  &lt;/div&gt;

  &lt;div class=&quot;border border-[#d3d3d3] dark:border-[#1b2e4b] rounded&quot;&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;p-4 w-full flex items-center text-white-dark dark:bg-[#1b2e4b]&quot;
      :class=&quot;{ '!text-primary': accordians4 === 3 }&quot;
      @click=&quot;accordians4 === 3 ? (accordians4 = null) : (accordians4 = 3)&quot;
    &gt;
      Collapsible Group Item #3
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;accordians4 === 3&quot;&gt;
      &lt;div class=&quot;p-4 text-[13px] border-t border-[#d3d3d3] dark:border-[#1b2e4b]&quot;&gt;
        &lt;p&gt;
          Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa
          nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft
          beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt
          you probably haven't heard of them accusamus labore sustainable VHS.
        &lt;/p&gt;
        &lt;button type=&quot;button&quot; class=&quot;btn btn-primary mt-4&quot;&gt;Accept&lt;/button&gt;
      &lt;/div&gt;
    &lt;/vue-collapsible&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref } from 'vue';
import VueCollapsible from 'vue-height-collapsible/vue3';
const accordians4: any = ref(1);
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts" setup>
    import { ref } from 'vue';
    import highlight from '@/components/plugins/highlight.vue';
    import codePreview from '@/composables/codePreview';
    import VueCollapsible from 'vue-height-collapsible/vue3';
    import { useMeta } from '@/composables/use-meta';

    import IconBell from '@/components/icon/icon-bell.vue';
    import IconCode from '@/components/icon/icon-code.vue';
    import IconCaretDown from '@/components/icon/icon-caret-down.vue';
    import IconAirplay from '@/components/icon/icon-airplay.vue';
    import IconBox from '@/components/icon/icon-box.vue';
    import IconLayout from '@/components/icon/icon-layout.vue';

    useMeta({ title: 'Accordions' });

    const { codeArr, toggleCode } = codePreview();
    const accordians1: any = ref(1);
    const accordians2: any = ref(1);
    const accordians3: any = ref(1);
    const accordians4: any = ref(1);
</script>
