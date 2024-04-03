<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Elements</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Badges</span>
            </li>
        </ul>
        <div class="pt-5 grid grid-cols-1 lg:grid-cols-2 gap-6">
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Basic</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code1')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        >
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex flex-wrap items-center justify-center gap-3">
                        <span class="badge bg-primary">Primary</span>
                        <span class="badge bg-secondary">Secondary</span>
                        <span class="badge bg-success">Success</span>
                        <span class="badge bg-danger">Danger</span>
                        <span class="badge bg-warning">Warning</span>
                        <span class="badge bg-info">Info</span>
                        <span class="badge bg-dark">Dark</span>
                    </div>
                </div>
                <template v-if="codeArr.includes('code1')">
                    <highlight>
                        <pre>
&lt;!-- primary --&gt;
&lt;span class=&quot;badge bg-primary&quot;&gt;Primary&lt;/span&gt;

&lt;!-- secondary --&gt;
&lt;span class=&quot;badge bg-secondary&quot;&gt;Secondary&lt;/span&gt;

&lt;!-- success --&gt;
&lt;span class=&quot;badge bg-success&quot;&gt;Success&lt;/span&gt;

&lt;!-- danger --&gt;
&lt;span class=&quot;badge bg-danger&quot;&gt;Danger&lt;/span&gt;

&lt;!-- warning --&gt;
&lt;span class=&quot;badge bg-warning&quot;&gt;Warning&lt;/span&gt;

&lt;!-- info --&gt;
&lt;span class=&quot;badge bg-info&quot;&gt;Info&lt;/span&gt;

&lt;!-- dark --&gt;
&lt;span class=&quot;badge bg-dark&quot;&gt;Dark&lt;/span&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Outline</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code2')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        >
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex flex-wrap items-center justify-center gap-3">
                        <span class="badge badge-outline-primary">Primary</span>
                        <span class="badge badge-outline-secondary">Secondary</span>
                        <span class="badge badge-outline-success">Success</span>
                        <span class="badge badge-outline-danger">Danger</span>
                        <span class="badge badge-outline-warning">Warning</span>
                        <span class="badge badge-outline-info">Info</span>
                        <span class="badge badge-outline-dark">Dark</span>
                    </div>
                </div>
                <template v-if="codeArr.includes('code2')">
                    <highlight>
                        <pre>
&lt;!-- primary outline --&gt;
&lt;span class=&quot;badge badge-outline-primary&quot;&gt;Primary&lt;/span&gt;

&lt;!-- secondary outline --&gt;
&lt;span class=&quot;badge badge-outline-secondary&quot;&gt;Secondary&lt;/span&gt;

&lt;!-- success outline --&gt;
&lt;span class=&quot;badge badge-outline-success&quot;&gt;Success&lt;/span&gt;

&lt;!-- danger outline --&gt;
&lt;span class=&quot;badge badge-outline-danger&quot;&gt;Danger&lt;/span&gt;

&lt;!-- warning outline --&gt;
&lt;span class=&quot;badge badge-outline-warning&quot;&gt;Warning&lt;/span&gt;

&lt;!-- info outline --&gt;
&lt;span class=&quot;badge badge-outline-info&quot;&gt;Info&lt;/span&gt;

&lt;!-- dark outline --&gt;
&lt;span class=&quot;badge badge-outline-dark&quot;&gt;Dark&lt;/span&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Pills</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code3')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        >
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex w-full">
                        <div class="flex items-center justify-center w-1/2">
                            <span class="badge bg-primary rounded-full">Primary</span>
                        </div>
                        <div class="flex items-center justify-center w-1/2">
                            <span class="badge badge-outline-primary rounded-full">Primary</span>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code3')">
                    <highlight>
                        <pre>
&lt;!-- pills --&gt;
&lt;div class=&quot;flex items-center justify-center w-1/2&quot;&gt;
  &lt;span class=&quot;badge bg-primary rounded-full&quot;&gt;Primary&lt;/span&gt;
&lt;/div&gt;

&lt;!-- pills outline --&gt;
&lt;div class=&quot;flex items-center justify-center w-1/2&quot;&gt;
  &lt;span class=&quot;badge badge-outline-primary rounded-full&quot;&gt;Primary&lt;/span&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Classic</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code4')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        >
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex w-full">
                        <div class="flex items-center justify-center w-1/2">
                            <span class="badge bg-primary rounded-none">Primary</span>
                        </div>
                        <div class="flex items-center justify-center w-1/2">
                            <span class="badge badge-outline-primary rounded-none">Primary</span>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code4')">
                    <highlight>
                        <pre>
&lt;!-- badge --&gt;
&lt;div class=&quot;flex items-center justify-center w-1/2&quot;&gt;
  &lt;span class=&quot;badge bg-primary rounded-none&quot;&gt;Primary&lt;/span&gt;
&lt;/div&gt;

&lt;!-- badge outline --&gt;
&lt;div class=&quot;flex items-center justify-center w-1/2&quot;&gt;
  &lt;span class=&quot;badge badge-outline-primary rounded-none&quot;&gt;Primary&lt;/span&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Badges with Heading</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code5')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        >
                    </a>
                </div>
                <div class="mb-5 dark:text-white-dark">
                    <p class="mb-5">Badges scale to match the size of the immediate parent element by using relative font sizing and em units.</p>
                    <div class="space-y-2 prose dark:prose-headings:text-white-dark">
                        <h1>Example heading <span class="badge bg-primary">Primary</span></h1>
                        <h2>Example heading <span class="badge bg-success">Success</span></h2>
                        <h3>Example heading <span class="badge bg-info">Info</span></h3>
                        <h4>Example heading <span class="badge bg-warning">Warning</span></h4>
                        <h5>Example heading <span class="badge bg-danger">Danger</span></h5>
                        <h6>Example heading <span class="badge bg-dark">Dark</span></h6>
                    </div>
                </div>
                <template v-if="codeArr.includes('code5')">
                    <highlight>
                        <pre>
&lt;!-- Badges with Heading --&gt;
&lt;div class=&quot;space-y-2 prose dark:prose-headings:text-white-dark&quot;&gt;
  &lt;h1&gt;Example heading &lt;span class=&quot;badge bg-primary&quot;&gt;Primary&lt;/span&gt;&lt;/h1&gt;

  &lt;h2&gt;Example heading &lt;span class=&quot;badge bg-success&quot;&gt;Success&lt;/span&gt;&lt;/h2&gt;

  &lt;h3&gt;Example heading &lt;span class=&quot;badge bg-info&quot;&gt;Info&lt;/span&gt;&lt;/h3&gt;

  &lt;h4&gt;Example heading &lt;span class=&quot;badge bg-warning&quot;&gt;Warning&lt;/span&gt;&lt;/h4&gt;

  &lt;h5&gt;Example heading &lt;span class=&quot;badge bg-danger&quot;&gt;Danger&lt;/span&gt;&lt;/h5&gt;

  &lt;h6&gt;Example heading &lt;span class=&quot;badge bg-dark&quot;&gt;Dark&lt;/span&gt;&lt;/h6&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Custom Badges</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code6')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        >
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex flex-wrap items-center justify-center gap-3">
                        <button type="button" class="btn btn-primary my-4">
                            <span class="flex items-center">
                                <icon-facebook class="w-4.5 h-4.5 ltr:mr-1 rtl:ml-1 shrink-0"/>
                                Facebook</span
                            >
                            <span class="badge absolute ltr:right-0 rtl:left-0 -top-3 bg-danger p-0.5 px-1.5 rounded-full">9</span>
                        </button>
                        <button type="button" class="btn btn-info my-4">
                            <span>Twitter</span><span class="badge absolute ltr:right-0 rtl:left-0 -top-3 bg-danger p-0.5 px-1.5 rounded-full">4</span>
                        </button>
                        <button type="button" class="btn btn-secondary px-5 my-4">
                            <span>
                                <icon-settings class="w-5 h-5"/>
                            </span>
                            <span class="badge absolute ltr:right-0 rtl:left-0 -top-3 bg-danger p-0.5 px-1.5 rounded-full">8</span>
                        </button>
                        <button type="button" class="btn btn-dark my-4">
                            Notifications<span class="badge my-0 bg-white-light text-black ltr:ml-4 rtl:mr-4">4</span>
                        </button>
                        <div class="flex flex-wrap items-center justify-center gap-3">
                            <span class="badge bg-warning p-0 ltr:pr-4 rtl:pl-4 my-4 rounded-full flex items-center text-base">
                                <img src="/assets/images/profile-34.jpeg" alt="" class="w-10 h-10 rounded-full object-cover" /><span class="ltr:ml-2 rtl:mr-2"
                                    >John Doe</span
                                ></span
                            >
                            <span class="badge bg-danger p-0 ltr:pr-4 rtl:pl-4 my-4 rounded-full flex items-center text-base">
                                <img src="/assets/images/profile-34.jpeg" alt="" class="w-10 h-10 rounded-full object-cover" /><span class="ltr:ml-2 rtl:mr-2"
                                    >John Doe</span
                                >
                                <span class="ltr:ml-4 rtl:mr-4 cursor-pointer hover:opacity-90">x</span></span
                            >
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code6')">
                    <highlight>
                        <pre>
&lt;!-- icon with text --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-primary my-4&quot;&gt;
  &lt;span class=&quot;flex items-center&quot;&gt; &lt;svg&gt; ... &lt;/svg&gt; Facebook&lt;/span&gt;
  &lt;span class=&quot;badge absolute ltr:right-0 rtl:left-0 -top-3 bg-danger p-0.5 px-1.5 rounded-full&quot;&gt;9&lt;/span&gt;
&lt;/button&gt;

&lt;!-- text --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-info my-4&quot;&gt;&lt;span&gt;Twitter&lt;/span&gt;&lt;span class=&quot;badge absolute ltr:right-0 rtl:left-0 -top-3 bg-danger p-0.5 px-1.5 rounded-full&quot;&gt;4&lt;/span&gt;&lt;/button&gt;

&lt;!-- icon --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-secondary px-5 my-4&quot;&gt;
  &lt;span&gt;&lt;svg&gt; ... &lt;/svg&gt;&lt;/span&gt;
  &lt;span class=&quot;badge absolute ltr:right-0 rtl:left-0 -top-3 bg-danger p-0.5 px-1.5 rounded-full&quot;&gt;8&lt;/span&gt;
&lt;/button&gt;

&lt;!-- square --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-dark my-4&quot;&gt;Notifications&lt;span class=&quot;badge my-0 bg-white-light text-black ltr:ml-4 rtl:mr-4&quot;&gt;4&lt;/span&gt;&lt;/button&gt;

&lt;!-- rounded --&gt;
&lt;span class=&quot;badge bg-warning p-0 ltr:pr-4 rtl:pl-4 my-4 rounded-full flex items-center text-base&quot;
  &gt;&lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-10 h-10 rounded-full object-cover&quot; /&gt;&lt;span class=&quot;ltr:ml-2 rtl:mr-2&quot;&gt;John Doe&lt;/span&gt;&lt;/span
&gt;

&lt;!-- rounded with icon --&gt;
&lt;span class=&quot;badge bg-danger p-0 ltr:pr-4 rtl:pl-4 my-4 rounded-full flex items-center text-base&quot;
  &gt;&lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-10 h-10 rounded-full object-cover&quot; /&gt;&lt;span class=&quot;ltr:ml-2 rtl:mr-2&quot;&gt;John Doe&lt;/span
  &gt;&lt;span class=&quot;ltr:ml-4 rtl:mr-4 cursor-pointer hover:opacity-90&quot;&gt;x&lt;/span&gt;&lt;/span
&gt;
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
    import IconFacebook from '@/components/icon/icon-facebook.vue';
    import IconSettings from '@/components/icon/icon-settings.vue';

    useMeta({ title: 'Badges' });

    const { codeArr, toggleCode } = codePreview();
</script>
