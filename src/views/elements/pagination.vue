<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Elements</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Pagination</span>
            </li>
        </ul>
        <div class="pt-5 grid grid-cols-1 xl:grid-cols-2 gap-6">
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Default</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code1')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <div class="flex justify-center flex-col w-full">
                        <ul class="inline-flex items-center space-x-1 rtl:space-x-reverse m-auto mb-4">
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition text-dark hover:text-primary border-2 border-[#e0e6ed] dark:border-[#191e3a] hover:border-primary dark:hover:border-primary dark:text-white-light"
                                >
                                    First
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition text-dark hover:text-primary border-2 border-[#e0e6ed] dark:border-[#191e3a] hover:border-primary dark:hover:border-primary dark:text-white-light"
                                >
                                    Prev
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition text-dark hover:text-primary border-2 border-[#e0e6ed] dark:border-[#191e3a] hover:border-primary dark:hover:border-primary dark:text-white-light"
                                >
                                    1
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition text-primary border-2 border-primary dark:border-primary dark:text-white-light"
                                >
                                    2
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition text-dark hover:text-primary border-2 border-[#e0e6ed] dark:border-[#191e3a] hover:border-primary dark:hover:border-primary dark:text-white-light"
                                >
                                    3
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition text-dark hover:text-primary border-2 border-[#e0e6ed] dark:border-[#191e3a] hover:border-primary dark:hover:border-primary dark:text-white-light"
                                >
                                    Next
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition text-dark hover:text-primary border-2 border-[#e0e6ed] dark:border-[#191e3a] hover:border-primary dark:hover:border-primary dark:text-white-light"
                                >
                                    Last
                                </button>
                            </li>
                        </ul>
                        <ul class="inline-flex items-center space-x-1 rtl:space-x-reverse m-auto">
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition text-dark hover:text-primary border-2 border-[#e0e6ed] dark:border-[#191e3a] hover:border-primary dark:hover:border-primary dark:text-white-light"
                                >
                                    Prev
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition text-dark hover:text-primary border-2 border-[#e0e6ed] dark:border-[#191e3a] hover:border-primary dark:hover:border-primary dark:text-white-light"
                                >
                                    1
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition text-primary border-2 border-primary dark:border-primary dark:text-white-light"
                                >
                                    2
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition text-dark hover:text-primary border-2 border-[#e0e6ed] dark:border-[#191e3a] hover:border-primary dark:hover:border-primary dark:text-white-light"
                                >
                                    3
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition text-dark hover:text-primary border-2 border-[#e0e6ed] dark:border-[#191e3a] hover:border-primary dark:hover:border-primary dark:text-white-light"
                                >
                                    Next
                                </button>
                            </li>
                        </ul>
                    </div>
                </div>
                <template v-if="codeArr.includes('code1')">
                    <highlight>
                        <pre>
&lt;!-- default --&gt;
&lt;ul class=&quot;inline-flex items-center space-x-1 rtl:space-x-reverse m-auto mb-4&quot;&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        text-dark
        hover:text-primary
        border-2 border-[#e0e6ed]
        dark:border-[#191e3a]
        hover:border-primary
        dark:hover:border-primary dark:text-white-light
      &quot;
    &gt;
      First
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        text-dark
        hover:text-primary
        border-2 border-[#e0e6ed]
        dark:border-[#191e3a]
        hover:border-primary
        dark:hover:border-primary dark:text-white-light
      &quot;
    &gt;
      Prev
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        text-dark
        hover:text-primary
        border-2 border-[#e0e6ed]
        dark:border-[#191e3a]
        hover:border-primary
        dark:hover:border-primary dark:text-white-light
      &quot;
    &gt;
      1
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button type=&quot;button&quot; class=&quot;flex justify-center font-semibold px-3.5 py-2 rounded transition text-primary border-2 border-primary dark:border-primary dark:text-white-light&quot;&gt;2&lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        text-dark
        hover:text-primary
        border-2 border-[#e0e6ed]
        dark:border-[#191e3a]
        hover:border-primary
        dark:hover:border-primary dark:text-white-light
      &quot;
    &gt;
      3
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        text-dark
        hover:text-primary
        border-2 border-[#e0e6ed]
        dark:border-[#191e3a]
        hover:border-primary
        dark:hover:border-primary dark:text-white-light
      &quot;
    &gt;
      Next
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        text-dark
        hover:text-primary
        border-2 border-[#e0e6ed]
        dark:border-[#191e3a]
        hover:border-primary
        dark:hover:border-primary dark:text-white-light
      &quot;
    &gt;
      Last
    &lt;/button&gt;
  &lt;/li&gt;
&lt;/ul&gt;

&lt;!-- default --&gt;
&lt;ul class=&quot;inline-flex items-center space-x-1 rtl:space-x-reverse m-auto&quot;&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        text-dark
        hover:text-primary
        border-2 border-[#e0e6ed]
        dark:border-[#191e3a]
        hover:border-primary
        dark:hover:border-primary dark:text-white-light
      &quot;
    &gt;
      Prev
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        text-dark
        hover:text-primary
        border-2 border-[#e0e6ed]
        dark:border-[#191e3a]
        hover:border-primary
        dark:hover:border-primary dark:text-white-light
      &quot;
    &gt;
      1
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button type=&quot;button&quot; class=&quot;flex justify-center font-semibold px-3.5 py-2 rounded transition text-primary border-2 border-primary dark:border-primary dark:text-white-light&quot;&gt;2&lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        text-dark
        hover:text-primary
        border-2 border-[#e0e6ed]
        dark:border-[#191e3a]
        hover:border-primary
        dark:hover:border-primary dark:text-white-light
      &quot;
    &gt;
      3
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        text-dark
        hover:text-primary
        border-2 border-[#e0e6ed]
        dark:border-[#191e3a]
        hover:border-primary
        dark:hover:border-primary dark:text-white-light
      &quot;
    &gt;
      Next
    &lt;/button&gt;
  &lt;/li&gt;
&lt;/ul&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Solid</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code2')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <div class="flex justify-center flex-col w-full">
                        <ul class="inline-flex items-center space-x-1 rtl:space-x-reverse m-auto mb-4">
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    First
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    Prev
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    1
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-primary text-white dark:text-white-light dark:bg-primary"
                                >
                                    2
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    3
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    Next
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    Last
                                </button>
                            </li>
                        </ul>
                        <ul class="inline-flex items-center space-x-1 rtl:space-x-reverse m-auto">
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    Prev
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    1
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-primary text-white dark:text-white-light dark:bg-primary"
                                >
                                    2
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    3
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    Next
                                </button>
                            </li>
                        </ul>
                    </div>
                </div>
                <template v-if="codeArr.includes('code2')">
                    <highlight>
                        <pre>
&lt;!-- solid --&gt;
&lt;ul class=&quot;inline-flex items-center space-x-1 rtl:space-x-reverse m-auto mb-4&quot;&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      First
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      Prev
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      1
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;&lt;button type=&quot;button&quot; class=&quot;flex justify-center font-semibold px-3.5 py-2 rounded transition bg-primary text-white dark:text-white-light dark:bg-primary&quot;&gt;2&lt;/button&gt;&lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      3
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      Next
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      Last
    &lt;/button&gt;
  &lt;/li&gt;
&lt;/ul&gt;

&lt;!-- solid --&gt;
&lt;ul class=&quot;inline-flex items-center space-x-1 rtl:space-x-reverse m-auto&quot;&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      Prev
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      1
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;&lt;button type=&quot;button&quot; class=&quot;flex justify-center font-semibold px-3.5 py-2 rounded transition bg-primary text-white dark:text-white-light dark:bg-primary&quot;&gt;2&lt;/button&gt;&lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      3
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      Next
    &lt;/button&gt;
  &lt;/li&gt;
&lt;/ul&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">With Icons</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code3')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <div class="flex justify-center flex-col w-full">
                        <ul class="inline-flex items-center space-x-1 rtl:space-x-reverse m-auto mb-4">
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-carets-down class="rotate-90 rtl:-rotate-90" />
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-caret-down class="w-5 h-5 rotate-90 rtl:-rotate-90" />
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    1
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-primary text-white dark:text-white-light dark:bg-primary"
                                >
                                    2
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    3
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-caret-down class="w-5 h-5 -rotate-90 rtl:rotate-90" />
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-carets-down class="-rotate-90 rtl:rotate-90" />
                                </button>
                            </li>
                        </ul>
                        <ul class="inline-flex items-center space-x-1 rtl:space-x-reverse m-auto">
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-caret-down class="w-5 h-5 rotate-90 rtl:-rotate-90" />
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    1
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-primary text-white dark:text-white-light dark:bg-primary"
                                >
                                    2
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    3
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-caret-down class="w-5 h-5 -rotate-90 rtl:rotate-90" />
                                </button>
                            </li>
                        </ul>
                    </div>
                </div>
                <template v-if="codeArr.includes('code3')">
                    <highlight>
                        <pre>
&lt;!-- with icons --&gt;
&lt;ul class=&quot;inline-flex items-center space-x-1 rtl:space-x-reverse m-auto mb-4&quot;&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      1
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button type=&quot;button&quot; class=&quot;flex justify-center font-semibold px-3.5 py-2 rounded transition bg-primary text-white dark:text-white-light dark:bg-primary&quot;&gt;2&lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      3
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
&lt;/ul&gt;

&lt;!-- with icons --&gt;
&lt;ul class=&quot;inline-flex items-center space-x-1 rtl:space-x-reverse m-auto&quot;&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      1
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button type=&quot;button&quot; class=&quot;flex justify-center font-semibold px-3.5 py-2 rounded transition bg-primary text-white dark:text-white-light dark:bg-primary&quot;&gt;2&lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      3
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
&lt;/ul&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">With Icons and Rounded</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code4')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <div class="flex justify-center flex-col w-full">
                        <ul class="inline-flex items-center space-x-1 rtl:space-x-reverse m-auto mb-4">
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold p-2 rounded-full transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-carets-down class="rotate-90 rtl:-rotate-90" />
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold p-2 rounded-full transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-caret-down class="w-5 h-5 rotate-90 rtl:-rotate-90" />
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded-full transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    1
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded-full transition bg-primary text-white dark:text-white-light dark:bg-primary"
                                >
                                    2
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded-full transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    3
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold p-2 rounded-full transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-caret-down class="w-5 h-5 -rotate-90 rtl:rotate-90" />
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold p-2 rounded-full transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-carets-down class="-rotate-90 rtl:rotate-90" />
                                </button>
                            </li>
                        </ul>
                        <ul class="inline-flex items-center space-x-1 rtl:space-x-reverse m-auto">
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold p-2 rounded-full transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-caret-down class="w-5 h-5 rotate-90 rtl:-rotate-90" />
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded-full transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    1
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded-full transition bg-primary text-white dark:text-white-light dark:bg-primary"
                                >
                                    2
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 rounded-full transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    3
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold p-2 rounded-full transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-caret-down class="w-5 h-5 -rotate-90 rtl:rotate-90" />
                                </button>
                            </li>
                        </ul>
                    </div>
                </div>
                <template v-if="codeArr.includes('code4')">
                    <highlight>
                        <pre>
&lt;!-- with icons rounded --&gt;
&lt;ul class=&quot;inline-flex items-center space-x-1 rtl:space-x-reverse m-auto mb-4&quot;&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        p-2
        rounded-full
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        p-2
        rounded-full
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded-full
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      1
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button type=&quot;button&quot; class=&quot;flex justify-center font-semibold px-3.5 py-2 rounded-full transition bg-primary text-white dark:text-white-light dark:bg-primary&quot;&gt;2&lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded-full
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      3
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        p-2
        rounded-full
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        p-2
        rounded-full
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
&lt;/ul&gt;

&lt;!-- with icons rounded --&gt;
&lt;ul class=&quot;inline-flex items-center space-x-1 rtl:space-x-reverse m-auto&quot;&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        p-2
        rounded-full
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded-full
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      1
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button type=&quot;button&quot; class=&quot;flex justify-center font-semibold px-3.5 py-2 rounded-full transition bg-primary text-white dark:text-white-light dark:bg-primary&quot;&gt;2&lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        rounded-full
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      3
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        p-2
        rounded-full
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
&lt;/ul&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">No Spacing</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code5')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <div class="flex justify-center flex-col w-full">
                        <ul class="inline-flex items-center m-auto mb-4">
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold ltr:rounded-l-full rtl:rounded-r-full px-3.5 py-2 transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-carets-down class="rotate-90 rtl:-rotate-90" />
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-caret-down class="w-5 h-5 rotate-90 rtl:-rotate-90" />
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    1
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 transition bg-primary text-white dark:text-white-light dark:bg-primary"
                                >
                                    2
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    3
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-caret-down class="w-5 h-5 -rotate-90 rtl:rotate-90" />
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold ltr:rounded-r-full rtl:rounded-l-full px-3.5 py-2 transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-carets-down class="-rotate-90 rtl:rotate-90" />
                                </button>
                            </li>
                        </ul>
                        <ul class="inline-flex items-center m-auto">
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold ltr:rounded-l-full rtl:rounded-r-full px-3.5 py-2 transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-caret-down class="w-5 h-5 rotate-90 rtl:-rotate-90" />
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    1
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 transition bg-primary text-white dark:text-white-light dark:bg-primary"
                                >
                                    2
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold px-3.5 py-2 transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    3
                                </button>
                            </li>
                            <li>
                                <button
                                    type="button"
                                    class="flex justify-center font-semibold ltr:rounded-r-full rtl:rounded-l-full px-3.5 py-2 transition bg-white-light text-dark hover:text-white hover:bg-primary dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary"
                                >
                                    <icon-caret-down class="w-5 h-5 -rotate-90 rtl:rotate-90" />
                                </button>
                            </li>
                        </ul>
                    </div>
                </div>
                <template v-if="codeArr.includes('code5')">
                    <highlight>
                        <pre>
&lt;!-- no spacing --&gt;
&lt;ul class=&quot;inline-flex items-center m-auto mb-4&quot;&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        ltr:rounded-l-full
        rtl:rounded-r-full
        px-3.5
        py-2
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      1
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button type=&quot;button&quot; class=&quot;flex justify-center font-semibold px-3.5 py-2 transition bg-primary text-white dark:text-white-light dark:bg-primary&quot;&gt;2&lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      3
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        ltr:rounded-r-full
        rtl:rounded-l-full
        px-3.5
        py-2
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
&lt;/ul&gt;

&lt;!-- no spacing --&gt;
&lt;ul class=&quot;inline-flex items-center m-auto&quot;&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        ltr:rounded-l-full
        rtl:rounded-r-full
        px-3.5
        py-2
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      1
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button type=&quot;button&quot; class=&quot;flex justify-center font-semibold px-3.5 py-2 transition bg-primary text-white dark:text-white-light dark:bg-primary&quot;&gt;2&lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        px-3.5
        py-2
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      3
    &lt;/button&gt;
  &lt;/li&gt;
  &lt;li&gt;
    &lt;button
      type=&quot;button&quot;
      class=&quot;
        flex
        justify-center
        font-semibold
        ltr:rounded-r-full
        rtl:rounded-l-full
        px-3.5
        py-2
        transition
        bg-white-light
        text-dark
        hover:text-white hover:bg-primary
        dark:text-white-light dark:bg-[#191e3a] dark:hover:bg-primary
      &quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/button&gt;
  &lt;/li&gt;
&lt;/ul&gt;
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
    import IconCaretsDown from '@/components/icon/icon-carets-down.vue';
    import IconCaretDown from '@/components/icon/icon-caret-down.vue';

    useMeta({ title: 'Pagination' });

    const { codeArr, toggleCode } = codePreview();
</script>
