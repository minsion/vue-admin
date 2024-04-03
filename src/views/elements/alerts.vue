<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Elements</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Alerts</span>
            </li>
        </ul>
        <div class="pt-5 space-y-8">
            <!-- default -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Default Alerts</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code1')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-5 mb-5">
                    <div class="flex items-center p-3.5 rounded text-primary bg-primary-light dark:bg-primary-dark-light">
                        <span class="ltr:pr-2 rtl:pl-2"
                            ><strong class="ltr:mr-1 rtl:ml-1">Primary!</strong>Lorem Ipsum is simply dummy text of the printing.</span
                        >
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                    <div class="flex items-center p-3.5 rounded text-secondary bg-secondary-light dark:bg-secondary-dark-light">
                        <span class="ltr:pr-2 rtl:pl-2"
                            ><strong class="ltr:mr-1 rtl:ml-1">Secondary!</strong>Lorem Ipsum is simply dummy text of the printing.</span
                        >
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                    <div class="flex items-center p-3.5 rounded text-success bg-success-light dark:bg-success-dark-light">
                        <span class="ltr:pr-2 rtl:pl-2"
                            ><strong class="ltr:mr-1 rtl:ml-1">Success!</strong>Lorem Ipsum is simply dummy text of the printing.</span
                        >
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                    <div class="flex items-center p-3.5 rounded text-warning bg-warning-light dark:bg-warning-dark-light">
                        <span class="ltr:pr-2 rtl:pl-2"
                            ><strong class="ltr:mr-1 rtl:ml-1">Warning!</strong>Lorem Ipsum is simply dummy text of the printing.</span
                        >
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                    <div class="flex items-center p-3.5 rounded text-danger bg-danger-light dark:bg-danger-dark-light">
                        <span class="ltr:pr-2 rtl:pl-2"
                            ><strong class="ltr:mr-1 rtl:ml-1">Danger!</strong>Lorem Ipsum is simply dummy text of the printing.</span
                        >
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                    <div class="flex items-center p-3.5 rounded text-info bg-info-light dark:bg-info-dark-light">
                        <span class="ltr:pr-2 rtl:pl-2"><strong class="ltr:mr-1 rtl:ml-1">Info!</strong>Lorem Ipsum is simply dummy text of the printing.</span>
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                </div>
                <template v-if="codeArr.includes('code1')">
                    <highlight>
                        <pre>
&lt;!-- primary --&gt;
&lt;div class=&quot;flex items-center p-3.5 rounded text-primary bg-primary-light dark:bg-primary-dark-light&quot;&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Primary!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;

&lt;!-- secondary --&gt;
&lt;div class=&quot;flex items-center p-3.5 rounded text-secondary bg-secondary-light dark:bg-secondary-dark-light&quot;&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Secondary!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;

&lt;!-- success --&gt;
&lt;div class=&quot;flex items-center p-3.5 rounded text-success bg-success-light dark:bg-success-dark-light&quot;&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Success!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;

&lt;!-- warning --&gt;
&lt;div class=&quot;flex items-center p-3.5 rounded text-warning bg-warning-light dark:bg-warning-dark-light&quot;&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Warning!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;

&lt;!-- danger --&gt;
&lt;div class=&quot;flex items-center p-3.5 rounded text-danger bg-danger-light dark:bg-danger-dark-light&quot;&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Danger!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;

&lt;!-- dark --&gt;
&lt;div class=&quot;flex items-center p-3.5 rounded text-info bg-info-light dark:bg-info-dark-light&quot;&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Info!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;
    </pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- Outline -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Outline Alerts</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code2')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-5 mb-5">
                    <div class="flex items-center p-3.5 rounded text-white-dark border border-primary">
                        <span class="ltr:pr-2 rtl:pl-2">
                            <strong class="ltr:mr-2 rtl:ml-2">Primary!</strong>Lorem Ipsum is simply dummy text of the printing.
                        </span>
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                    <div class="flex items-center border p-3.5 rounded text-white-dark border-danger">
                        <span class="ltr:pr-2 rtl:pl-2">
                            <strong class="ltr:mr-2 rtl:ml-2">Danger!</strong>Lorem Ipsum is simply dummy text of the printing.
                        </span>
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                </div>
                <template v-if="codeArr.includes('code2')">
                    <highlight>
                        <pre>
&lt;!-- primary --&gt;
&lt;div class=&quot;flex items-center p-3.5 rounded text-white-dark border border-primary&quot;&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt; &lt;strong class=&quot;ltr:mr-2 rtl:ml-2&quot;&gt;Primary!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing. &lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;

&lt;!-- danger --&gt;
&lt;div class=&quot;flex items-center border p-3.5 rounded text-white-dark border-danger&quot;&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt; &lt;strong class=&quot;ltr:mr-2 rtl:ml-2&quot;&gt;Danger!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing. &lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- Solid -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Solid Alerts</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code3')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-5 mb-5">
                    <div class="flex items-center p-3.5 rounded text-white bg-primary">
                        <span class="ltr:pr-2 rtl:pl-2">
                            <strong class="ltr:mr-1 rtl:ml-1">Warning!</strong>Lorem Ipsum is simply dummy text of the printing.
                        </span>
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                    <div class="flex items-center p-3.5 rounded text-white bg-warning">
                        <span class="ltr:pr-2 rtl:pl-2"><strong class="ltr:mr-1 rtl:ml-1">Info!</strong>Lorem Ipsum is simply dummy text of the printing.</span>
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                </div>
                <template v-if="codeArr.includes('code3')">
                    <highlight>
                        <pre>
&lt;!-- primary --&gt;
&lt;div class=&quot;flex items-center p-3.5 rounded text-white bg-primary&quot;&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt; &lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Warning!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing. &lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;

&lt;!-- warning --&gt;
&lt;div class=&quot;flex items-center p-3.5 rounded text-white bg-warning&quot;&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Info!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- Alerts with icon -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Alerts with icon</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code4')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-5 mb-5">
                    <div
                        class="relative flex items-center border p-3.5 rounded text-success bg-success-light border-success ltr:border-l-[64px] rtl:border-r-[64px] dark:bg-success-dark-light"
                    >
                        <span class="absolute ltr:-left-11 rtl:-right-11 inset-y-0 text-white w-6 h-6 m-auto">
                            <icon-info-triangle />
                        </span>
                        <span class="ltr:pr-2 rtl:pl-2"
                            ><strong class="ltr:mr-1 rtl:ml-1">Warning!</strong>Lorem Ipsum is simply dummy text of the printing.</span
                        >
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                    <div
                        class="relative flex items-center border p-3.5 rounded text-dark bg-dark-light border-dark ltr:border-r-[64px] rtl:border-l-[64px] dark:bg-dark-dark-light dark:text-white-light dark:border-white-light/20"
                    >
                        <span class="absolute ltr:-right-11 rtl:-left-11 inset-y-0 text-white w-6 h-6 m-auto">
                            <icon-settings />
                        </span>
                        <span class="ltr:pr-2 rtl:pl-2"
                            ><strong class="ltr:mr-1 rtl:ml-1">Warning!</strong>Lorem Ipsum is simply dummy text of the printing.</span
                        >
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                </div>
                <template v-if="codeArr.includes('code4')">
                    <highlight>
                        <pre>
&lt;!-- success --&gt;
&lt;div class=&quot;relative flex items-center border p-3.5 rounded text-success bg-success-light border-success ltr:border-l-[64px] rtl:border-r-[64px] dark:bg-success-dark-light&quot;&gt;
  &lt;span class=&quot;absolute ltr:-left-11 rtl:-right-11 inset-y-0 text-white w-6 h-6 m-auto&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/span&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Warning!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;

&lt;!-- warning --&gt;
&lt;div
  class=&quot;
    relative
    flex
    items-center
    border
    p-3.5
    rounded
    text-dark
    bg-dark-light
    border-dark
    ltr:border-r-[64px]
    rtl:border-l-[64px]
    dark:bg-dark-dark-light dark:text-white-light dark:border-white-light/20
  &quot;
&gt;
  &lt;span class=&quot;absolute ltr:-right-11 rtl:-left-11 inset-y-0 text-white w-6 h-6 m-auto&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/span&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Warning!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- Arrowed alert -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Arrowed Alerts</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code5')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-5 mb-5">
                    <div
                        class="relative flex items-center border p-3.5 rounded before:absolute before:top-1/2 ltr:before:left-0 rtl:before:right-0 rtl:before:rotate-180 before:-mt-2 before:border-l-8 before:border-t-8 before:border-b-8 before:border-t-transparent before:border-b-transparent before:border-l-inherit text-primary bg-primary-light !border-primary ltr:border-l-[64px] rtl:border-r-[64px] dark:bg-primary-dark-light"
                    >
                        <span class="absolute ltr:-left-11 rtl:-right-11 inset-y-0 text-white w-6 h-6 m-auto">
                            <icon-bell-bing class="w-6 h-6" />
                        </span>
                        <span class="ltr:pr-2 rtl:pl-2"
                            ><strong class="ltr:mr-1 rtl:ml-1">Warning!</strong>Lorem Ipsum is simply dummy text of the printing.</span
                        >
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                    <div
                        class="relative flex items-center border p-3.5 rounded before:inline-block before:absolute before:top-1/2 ltr:before:right-0 rtl:before:left-0 rtl:before:rotate-180 before:-mt-2 before:border-r-8 before:border-t-8 before:border-b-8 before:border-t-transparent before:border-b-transparent before:border-r-inherit text-danger bg-danger-light border-danger ltr:border-r-[64px] rtl:border-l-[64px] dark:bg-danger-dark-light"
                    >
                        <span class="absolute ltr:-right-11 rtl:-left-11 inset-y-0 text-white w-6 h-6 m-auto">
                            <icon-info-circle />
                        </span>
                        <span class="ltr:pr-2 rtl:pl-2"
                            ><strong class="ltr:mr-1 rtl:ml-1">Warning!</strong>Lorem Ipsum is simply dummy text of the printing.</span
                        >
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                </div>
                <template v-if="codeArr.includes('code5')">
                    <highlight>
                        <pre>
&lt;!-- primary --&gt;
&lt;div
  class=&quot;
    relative
    flex
    items-center
    border
    p-3.5
    rounded
    before:absolute before:top-1/2
    ltr:before:left-0
    rtl:before:right-0 rtl:before:rotate-180
    before:-mt-2 before:border-l-8 before:border-t-8 before:border-b-8 before:border-t-transparent before:border-b-transparent before:border-l-inherit
    text-primary
    bg-primary-light
    !border-primary
    ltr:border-l-[64px]
    rtl:border-r-[64px]
    dark:bg-primary-dark-light
  &quot;
&gt;
  &lt;span class=&quot;absolute ltr:-left-11 rtl:-right-11 inset-y-0 text-white w-6 h-6 m-auto&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/span&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Warning!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;

&lt;!-- primary --&gt;
&lt;div
  class=&quot;
    relative
    flex
    items-center
    border
    p-3.5
    rounded
    before:inline-block before:absolute before:top-1/2
    ltr:before:right-0
    rtl:before:left-0 rtl:before:rotate-180
    before:-mt-2 before:border-r-8 before:border-t-8 before:border-b-8 before:border-t-transparent before:border-b-transparent before:border-r-inherit
    text-danger
    bg-danger-light
    border-danger
    ltr:border-r-[64px]
    rtl:border-l-[64px]
    dark:bg-danger-dark-light
  &quot;
&gt;
  &lt;span class=&quot;absolute ltr:-right-11 rtl:-left-11 inset-y-0 text-white w-6 h-6 m-auto&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/span&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Warning!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- Custom alert -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Custom Alerts</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code6')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-5 mb-5">
                    <div class="flex items-center p-3.5 rounded text-white bg-info">
                        <span class="text-white w-6 h-6 ltr:mr-4 rtl:ml-4">
                            <icon-bell-bing class="w-6 h-6" />
                        </span>
                        <span><strong class="ltr:mr-1 rtl:ml-1">Warning!</strong>Lorem Ipsum is simply dummy text of the printing.</span>
                        <button type="button" class="btn btn-sm bg-white text-black ltr:ml-auto rtl:mr-auto">Accept</button>
                        <button type="button" class="ltr:ml-4 rtl:mr-4">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>

                    <div
                        class="flex items-center p-3.5 rounded text-white"
                        style="background: rgb(188, 26, 78); background: linear-gradient(135deg, rgba(188, 26, 78, 1) 0%, rgba(0, 79, 230, 1) 100%)"
                    >
                        <span class="ltr:pr-2 rtl:pl-2"
                            ><strong class="ltr:mr-1 rtl:ml-1">Warning!</strong>Lorem Ipsum is simply dummy text of the printing.</span
                        >
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>

                    <div class="flex items-center p-3.5 rounded text-white bg-[url('/assets/images/menu-heade.jpg')] bg-no-repeat bg-center bg-cover">
                        <span class="ltr:pr-2 rtl:pl-2"
                            ><strong class="ltr:mr-1 rtl:ml-1">Warning!</strong>Lorem Ipsum is simply dummy text of the printing.</span
                        >
                        <button type="button" class="ltr:ml-auto rtl:mr-auto hover:opacity-80">
                            <icon-x class="w-5 h-5" />
                        </button>
                    </div>
                </div>
                <template v-if="codeArr.includes('code6')">
                    <highlight>
                        <pre>
&lt;!-- info --&gt;
&lt;div class=&quot;flex items-center p-3.5 rounded text-white bg-info&quot;&gt;
  &lt;span class=&quot;text-white w-6 h-6 ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/span&gt;
  &lt;span&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Warning!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;btn btn-sm bg-white text-black ltr:ml-auto rtl:mr-auto&quot;&gt;Accept&lt;/button&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-4 rtl:mr-4&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;

&lt;!-- gradient --&gt;
&lt;div class=&quot;flex items-center p-3.5 rounded text-white&quot; style=&quot;background: rgb(188, 26, 78); background: linear-gradient(135deg, rgba(188, 26, 78, 1) 0%, rgba(0, 79, 230, 1) 100%)&quot;&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Warning!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
&lt;/div&gt;

&lt;!-- image --&gt;
&lt;div class=&quot;flex items-center p-3.5 rounded text-white bg-[url('/assets/images/menu-heade.jpg')] bg-no-repeat bg-center bg-cover&quot;&gt;
  &lt;span class=&quot;ltr:pr-2 rtl:pl-2&quot;&gt;&lt;strong class=&quot;ltr:mr-1 rtl:ml-1&quot;&gt;Warning!&lt;/strong&gt;Lorem Ipsum is simply dummy text of the printing.&lt;/span&gt;
  &lt;button type=&quot;button&quot; class=&quot;ltr:ml-auto rtl:mr-auto hover:opacity-80&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/button&gt;
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
    import IconX from '@/components/icon/icon-x.vue';
    import IconInfoTriangle from '@/components/icon/icon-info-triangle.vue';
    import IconSettings from '@/components/icon/icon-settings.vue';
    import IconBellBing from '@/components/icon/icon-bell-bing.vue';
    import IconInfoCircle from '@/components/icon/icon-info-circle.vue';

    useMeta({ title: 'Alerts' });

    const { codeArr, toggleCode } = codePreview();
</script>
