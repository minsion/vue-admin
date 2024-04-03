<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Elements</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Treeview</span>
            </li>
        </ul>
        <div class="pt-5 grid grid-cols-1 lg:grid-cols-2 gap-6">
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Animated</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code1')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <ul class="font-semibold">
                        <li class="py-[5px]">
                            <button type="button" @click="toggleTreeview1('css')">
                                <icon-caret-down
                                    class="w-5 h-5 text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2"
                                    :class="{ 'rotate-180': treeview1.includes('css') }"
                                />
                                <icon-folder class="text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2" />
                                CSS
                            </button>
                            <vue-collapsible :isOpen="treeview1.includes('css')">
                                <ul class="ltr:pl-14 rtl:pr-14">
                                    <li class="py-[5px]">
                                        <icon-txt-file class="w-4.5 h-4.5 text-primary inline ltr:mr-2 rtl:ml-2" />

                                        style.css
                                    </li>
                                </ul>
                            </vue-collapsible>
                        </li>
                        <li class="py-[5px]">
                            <button type="button" @click="toggleTreeview1('images')">
                                <icon-caret-down
                                    class="w-5 h-5 text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2"
                                    :class="{ 'rotate-180': treeview1.includes('images') }"
                                />
                                <icon-folder class="text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2" />
                                Images
                            </button>
                            <vue-collapsible :isOpen="treeview1.includes('images')">
                                <ul class="ltr:pl-14 rtl:pr-14">
                                    <li class="py-[5px]">
                                        <icon-txt-file class="w-4.5 h-4.5 text-primary inline ltr:mr-2 rtl:ml-2" />
                                        profile-16.jpeg
                                    </li>
                                    <li class="py-[5px]">
                                        <icon-txt-file class="w-4.5 h-4.5 text-primary inline ltr:mr-2 rtl:ml-2" />
                                        background.png
                                    </li>
                                    <li class="py-[5px]">
                                        <icon-txt-file class="w-4.5 h-4.5 text-primary inline ltr:mr-2 rtl:ml-2" />
                                        gallery.jpg
                                    </li>
                                </ul>
                            </vue-collapsible>
                        </li>
                        <li class="py-[5px]">
                            <button type="button" @click="toggleTreeview1('html')">
                                <icon-caret-down
                                    class="w-5 h-5 text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2"
                                    :class="{ 'rotate-180': treeview1.includes('html') }"
                                />
                                <icon-folder class="text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2" />
                                HTML
                            </button>
                            <vue-collapsible :isOpen="treeview1.includes('html')">
                                <ul class="ltr:pl-14 rtl:pr-14">
                                    <li class="py-[5px]">
                                        <button type="button" @click="toggleTreeview1('pages')">
                                            <icon-caret-down
                                                class="w-5 h-5 text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2"
                                                :class="{ 'rotate-180': treeview1.includes('pages') }"
                                            />
                                            <icon-folder class="text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2" />
                                            PAGES
                                        </button>
                                        <vue-collapsible :isOpen="treeview1.includes('pages')">
                                            <ul class="ltr:pl-14 rtl:pr-14">
                                                <li class="py-[5px]">
                                                    <icon-txt-file class="w-4.5 h-4.5 text-primary inline ltr:mr-2 rtl:ml-2" />
                                                    file name
                                                </li>
                                                <li class="py-[5px]">
                                                    <icon-txt-file class="w-4.5 h-4.5 text-primary inline ltr:mr-2 rtl:ml-2" />
                                                    file name
                                                </li>
                                                <li class="py-[5px]">
                                                    <icon-txt-file class="w-4.5 h-4.5 text-primary inline ltr:mr-2 rtl:ml-2" />
                                                    file name
                                                </li>
                                            </ul>
                                        </vue-collapsible>
                                    </li>
                                    <li class="py-[5px] ltr:pl-8 rtl:pr-8">
                                        <icon-txt-file class="w-4.5 h-4.5 text-primary inline ltr:mr-2 rtl:ml-2" />
                                        file name
                                    </li>
                                    <li class="py-[5px] ltr:pl-8 rtl:pr-8">
                                        <icon-txt-file class="w-4.5 h-4.5 text-primary inline ltr:mr-2 rtl:ml-2" />
                                        file name
                                    </li>
                                </ul>
                            </vue-collapsible>
                        </li>
                        <li class="py-[5px] ltr:pl-7 rtl:pr-7">
                            <icon-txt-file class="w-4.5 h-4.5 text-primary inline ltr:mr-2 rtl:ml-2" />
                            index.html
                        </li>
                        <li class="py-[5px] ltr:pl-7 rtl:pr-7">
                            <icon-txt-file class="w-4.5 h-4.5 text-primary inline ltr:mr-2 rtl:ml-2" />
                            components.html
                        </li>
                    </ul>
                </div>
                <template v-if="codeArr.includes('code1')">
                    <highlight>
                        <pre>
&lt;!-- animated --&gt;
&lt;ul class=&quot;font-semibold&quot;&gt;
  &lt;li class=&quot;py-[5px]&quot;&gt;
    &lt;button type=&quot;button&quot; @click=&quot;toggleTreeview1('css')&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      CSS
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;treeview1.includes('css')&quot;&gt;
      &lt;ul class=&quot;ltr:pl-14 rtl:pr-14&quot;&gt;
        &lt;li class=&quot;py-[5px]&quot;&gt;
          &lt;svg&gt; ... &lt;/svg&gt;
          style.css
        &lt;/li&gt;
      &lt;/ul&gt;
    &lt;/vue-collapsible&gt;
  &lt;/li&gt;
  &lt;li class=&quot;py-[5px]&quot;&gt;
    &lt;button type=&quot;button&quot; @click=&quot;toggleTreeview1('images')&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      Images
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;treeview1.includes('images')&quot;&gt;
      &lt;ul class=&quot;ltr:pl-14 rtl:pr-14&quot;&gt;
        &lt;li class=&quot;py-[5px]&quot;&gt;
          &lt;svg&gt; ... &lt;/svg&gt;
          profile-16.jpeg
        &lt;/li&gt;
        &lt;li class=&quot;py-[5px]&quot;&gt;&lt;svg&gt; ... &lt;/svg&gt;background.png&lt;/li&gt;
        &lt;li class=&quot;py-[5px]&quot;&gt;&lt;svg&gt; ... &lt;/svg&gt;gallery.jpg&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/vue-collapsible&gt;
  &lt;/li&gt;
  &lt;li class=&quot;py-[5px]&quot;&gt;
    &lt;button type=&quot;button&quot; @click=&quot;toggleTreeview1('html')&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      HTML
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;treeview1.includes('html')&quot;&gt;
      &lt;ul class=&quot;ltr:pl-14 rtl:pr-14&quot;&gt;
        &lt;li class=&quot;py-[5px]&quot;&gt;
          &lt;button type=&quot;button&quot; @click=&quot;toggleTreeview1('pages')&quot;&gt;
            &lt;svg&gt; ... &lt;/svg&gt;
            PAGES
          &lt;/button&gt;
          &lt;vue-collapsible :isOpen=&quot;treeview1.includes('pages')&quot;&gt;
            &lt;ul class=&quot;ltr:pl-14 rtl:pr-14&quot;&gt;
              &lt;li class=&quot;py-[5px]&quot;&gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                file name
              &lt;/li&gt;
              &lt;li class=&quot;py-[5px]&quot;&gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                file name
              &lt;/li&gt;
              &lt;li class=&quot;py-[5px]&quot;&gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                file name
              &lt;/li&gt;
            &lt;/ul&gt;
          &lt;/vue-collapsible&gt;
        &lt;/li&gt;
        &lt;li class=&quot;py-[5px] ltr:pl-8 rtl:pr-8&quot;&gt;&lt;svg&gt; ... &lt;/svg&gt;file name&lt;/li&gt;
        &lt;li class=&quot;py-[5px] ltr:pl-8 rtl:pr-8&quot;&gt;&lt;svg&gt; ... &lt;/svg&gt;file name&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/vue-collapsible&gt;
  &lt;/li&gt;
  &lt;li class=&quot;py-[5px] ltr:pl-7 rtl:pr-7&quot;&gt;&lt;svg&gt; ... &lt;/svg&gt;index.html&lt;/li&gt;
  &lt;li class=&quot;py-[5px] ltr:pl-7 rtl:pr-7&quot;&gt;&lt;svg&gt; ... &lt;/svg&gt;components.html&lt;/li&gt;
&lt;/ul&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref } from 'vue';
  import VueCollapsible from 'vue-height-collapsible/vue3';
  const treeview1: any = ref([]);
  const toggleTreeview1 = (name: string) =&gt; {
    if (treeview1.value.includes(name as never)) {
      treeview1.value = treeview1.value.filter((d) =&gt; d != name);
    } else {
      treeview1.value.push(name as never);
    }
  };
&lt;/script&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Basic</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code2')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <ul class="font-semibold no-animtion">
                        <li>
                            <button type="button" @click="toggleTreeview2('parent-node')">
                                <icon-folder-plus v-if="treeview2.includes('parent-node')" class="text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2" />
                                <icon-folder-minus v-else class="text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2" />
                                Parent Node
                            </button>
                            <vue-collapsible :isOpen="treeview2.includes('parent-node')">
                                <ul>
                                    <li class="py-[5px] ltr:pl-7 rtl:pr-7">
                                        <button type="button" @click="toggleTreeview2('img')">
                                            <icon-folder-plus v-if="treeview2.includes('img')" class="text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2" />
                                            <icon-folder-minus v-else class="text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2" />
                                            img
                                        </button>
                                        <vue-collapsible :isOpen="treeview2.includes('img')">
                                            <ul></ul>
                                        </vue-collapsible>
                                    </li>
                                    <li class="py-[5px] ltr:pl-7 rtl:pr-7">
                                        <button type="button" @click="toggleTreeview2('css')">
                                            <icon-folder-plus v-if="treeview2.includes('css')" class="text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2" />
                                            <icon-folder-minus v-else class="text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2" />
                                            css
                                        </button>
                                        <vue-collapsible :isOpen="treeview2.includes('css')">
                                            <ul>
                                                <li class="py-[5px] ltr:pl-7 rtl:pr-7 text-secondary">style.css</li>
                                            </ul>
                                        </vue-collapsible>
                                    </li>
                                    <li class="py-[5px] ltr:pl-7 rtl:pr-7">
                                        <button type="button" @click="toggleTreeview2('js')">
                                            <icon-folder-plus v-if="treeview2.includes('js')" class="text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2" />
                                            <icon-folder-minus v-else class="text-primary inline relative -top-1 ltr:mr-2 rtl:ml-2" />
                                            js
                                        </button>
                                        <vue-collapsible :isOpen="treeview2.includes('js')">
                                            <ul>
                                                <li class="py-[5px] ltr:pl-7 rtl:pr-7 text-secondary">script.js</li>
                                            </ul>
                                        </vue-collapsible>
                                    </li>
                                    <li class="py-[5px] ltr:pl-7 rtl:pr-7 text-secondary">index.html</li>
                                </ul>
                            </vue-collapsible>
                        </li>
                    </ul>
                </div>
                <template v-if="codeArr.includes('code2')">
                    <highlight>
                        <pre>
&lt;!-- basic --&gt;
&lt;ul class=&quot;font-semibold no-animtion&quot;&gt;
  &lt;li&gt;
    &lt;button type=&quot;button&quot; @click=&quot;toggleTreeview2('parent-node')&quot;&gt;
      &lt;svg&gt; ... &lt;/svg&gt;
      Parent Node
    &lt;/button&gt;
    &lt;vue-collapsible :isOpen=&quot;treeview2.includes('parent-node')&quot;&gt;
      &lt;ul&gt;
        &lt;li class=&quot;py-[5px] ltr:pl-7 rtl:pr-7&quot;&gt;
          &lt;button type=&quot;button&quot; @click=&quot;toggleTreeview2('img')&quot;&gt;
            &lt;svg&gt; ... &lt;/svg&gt;
            img
          &lt;/button&gt;
          &lt;vue-collapsible :isOpen=&quot;treeview2.includes('img')&quot;&gt;
            &lt;ul&gt;&lt;/ul&gt;
          &lt;/vue-collapsible&gt;
        &lt;/li&gt;
        &lt;li class=&quot;py-[5px] ltr:pl-7 rtl:pr-7&quot;&gt;
          &lt;button type=&quot;button&quot; @click=&quot;toggleTreeview2('css')&quot;&gt;
            &lt;svg&gt; ... &lt;/svg&gt;
            css
          &lt;/button&gt;
          &lt;vue-collapsible :isOpen=&quot;treeview2.includes('css')&quot;&gt;
            &lt;ul&gt;
              &lt;li class=&quot;py-[5px] ltr:pl-7 rtl:pr-7 text-secondary&quot;&gt;style.css&lt;/li&gt;
            &lt;/ul&gt;
          &lt;/vue-collapsible&gt;
        &lt;/li&gt;
        &lt;li class=&quot;py-[5px] ltr:pl-7 rtl:pr-7&quot;&gt;
          &lt;button type=&quot;button&quot; @click=&quot;toggleTreeview2('js')&quot;&gt;
            &lt;svg&gt; ... &lt;/svg&gt;
            js
          &lt;/button&gt;
          &lt;vue-collapsible :isOpen=&quot;treeview2.includes('js')&quot;&gt;
            &lt;ul&gt;
              &lt;li class=&quot;py-[5px] ltr:pl-7 rtl:pr-7 text-secondary&quot;&gt;script.js&lt;/li&gt;
            &lt;/ul&gt;
          &lt;/vue-collapsible&gt;
        &lt;/li&gt;
        &lt;li class=&quot;py-[5px] ltr:pl-7 rtl:pr-7 text-secondary&quot;&gt;index.html&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/vue-collapsible&gt;
  &lt;/li&gt;
&lt;/ul&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref } from 'vue';
  import VueCollapsible from 'vue-height-collapsible/vue3';
  const treeview2: any = ref(['parent-node']);
  const toggleTreeview2 = (name: string) =&gt; {
    if (treeview2.value.includes(name as never)) {
      treeview2.value = treeview2.value.filter((d) =&gt; d != name);
    } else {
      treeview2.value.push(name as never);
    }
  };
&lt;/script&gt;
</pre
                        >
                    </highlight>
                </template>
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

    import IconCode from '@/components/icon/icon-code.vue';
    import IconCaretDown from '@/components/icon/icon-caret-down.vue';
    import IconFolder from '@/components/icon/icon-folder.vue';
    import IconTxtFile from '@/components/icon/icon-txt-file.vue';
    import IconFolderPlus from '@/components/icon/icon-folder-plus.vue';
    import IconFolderMinus from '@/components/icon/icon-folder-minus.vue';

    useMeta({ title: 'Treeview' });

    const { codeArr, toggleCode } = codePreview();
    const treeview1: any = ref(['images']);
    const treeview2: any = ref(['parent-node']);

    const toggleTreeview1 = (name: string) => {
        if (treeview1.value.includes(name as never)) {
            treeview1.value = treeview1.value.filter((d) => d != name);
        } else {
            treeview1.value.push(name as never);
        }
    };

    const toggleTreeview2 = (name: string) => {
        if (treeview2.value.includes(name as never)) {
            treeview2.value = treeview2.value.filter((d) => d != name);
        } else {
            treeview2.value.push(name as never);
        }
    };
</script>
