<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Forms</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Select2</span>
            </li>
        </ul>
        <div class="pt-5 space-y-8">
            <div class="panel p-3 flex items-center text-primary overflow-x-auto whitespace-nowrap">
                <div class="ring-2 ring-primary/30 rounded-full bg-primary text-white p-1.5 ltr:mr-3 rtl:ml-3">
                    <icon-bell />
                </div>
                <span class="ltr:mr-3 rtl:ml-3">Documentation: </span
                ><a href="https://www.npmjs.com/package/@suadelabs/vue3-multiselect" target="_blank" class="block hover:underline"
                    >https://www.npmjs.com/package/@suadelabs/vue3-multiselect</a
                >
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                <!-- Basic -->
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
                        <multiselect
                            v-model="input1"
                            :options="options"
                            class="custom-multiselect"
                            :searchable="false"
                            :preselect-first="true"
                            :allow-empty="false"
                            selected-label=""
                            select-label=""
                            deselect-label=""
                        ></multiselect>
                    </div>
                    <template v-if="codeArr.includes('code1')">
                        <highlight>
                            <pre>
&lt;!-- basic --&gt;
&lt;multiselect
  v-model=&quot;input1&quot;
  :options=&quot;options&quot;
  class=&quot;custom-multiselect&quot;
  :searchable=&quot;false&quot;
  :preselect-first=&quot;true&quot;
  :allow-empty=&quot;false&quot;
  selected-label=&quot;&quot;
  select-label=&quot;&quot;
  deselect-label=&quot;&quot;
&gt;&lt;/multiselect&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref } from 'vue';
  import Multiselect from '@suadelabs/vue3-multiselect';
  import '@suadelabs/vue3-multiselect/dist/vue3-multiselect.css';

  const options = ref(['Orange', 'White', 'Purple']);
  const input1 = ref('Orange');
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Nested -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Nested</h5>
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
                        <multiselect
                            v-model="input2"
                            :options="options2"
                            class="custom-multiselect"
                            :searchable="false"
                            :allow-empty="false"
                            group-values="list"
                            group-label="group_name"
                            placeholder="Select Option"
                            track-by="name"
                            label="name"
                            :preselect-first="true"
                            selected-label=""
                            select-label=""
                            deselect-label=""
                        ></multiselect>
                    </div>
                    <template v-if="codeArr.includes('code2')">
                        <highlight>
                            <pre>
&lt;!-- nested --&gt;
&lt;multiselect
  v-model=&quot;input2&quot;
  :options=&quot;options2&quot;
  class=&quot;custom-multiselect&quot;
  :searchable=&quot;false&quot;
  :allow-empty=&quot;false&quot;
  group-values=&quot;list&quot;
  group-label=&quot;group_name&quot;
  placeholder=&quot;Select Option&quot;
  track-by=&quot;name&quot;
  label=&quot;name&quot;
  :preselect-first=&quot;true&quot;
  selected-label=&quot;&quot;
  select-label=&quot;&quot;
  deselect-label=&quot;&quot;
&gt;&lt;/multiselect&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref } from 'vue';
  import Multiselect from '@suadelabs/vue3-multiselect';
  import '@suadelabs/vue3-multiselect/dist/vue3-multiselect.css';

  const options2 = ref([
    {
      group_name: 'Group 1',
      list: [{ name: 'Orange' }, { name: 'White' }, { name: 'Purple' }],
    },
    {
      group_name: 'Group 2',
      list: [{ name: 'Yellow' }, { name: 'Red' }, { name: 'Green' }],
    },
    {
      group_name: 'Group 3',
      list: [{ name: 'Aqua' }, { name: 'Black' }, { name: 'Blue' }],
    },
  ]);
  const input2 = ref({ name: 'Orange' });
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Disabling options -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Disabling options</h5>
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
                        <multiselect
                            v-model="input3"
                            :options="options3"
                            class="custom-multiselect"
                            :searchable="false"
                            :allow-empty="false"
                            track-by="name"
                            label="name"
                            :preselect-first="true"
                            selected-label=""
                            select-label=""
                            deselect-label=""
                        ></multiselect>
                    </div>
                    <template v-if="codeArr.includes('code3')">
                        <highlight>
                            <pre>
&lt;!-- disabling options --&gt;
&lt;multiselect
  v-model=&quot;input3&quot;
  :options=&quot;options3&quot;
  class=&quot;custom-multiselect&quot;
  :searchable=&quot;false&quot;
  :allow-empty=&quot;false&quot;
  track-by=&quot;name&quot;
  label=&quot;name&quot;
  :preselect-first=&quot;true&quot;
  selected-label=&quot;&quot;
  select-label=&quot;&quot;
  deselect-label=&quot;&quot;
&gt;&lt;/multiselect&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref } from 'vue';
  import Multiselect from '@suadelabs/vue3-multiselect';
  import '@suadelabs/vue3-multiselect/dist/vue3-multiselect.css';

  const options3 = ref([{ name: 'Orange' }, { name: 'White', $isDisabled: true }, { name: 'Purple' }]);
  const input3 = ref({ name: 'Orange' });
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Placeholder -->
                <div class="panel lg:row-start-3">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Placeholder</h5>
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
                        <multiselect
                            v-model="input4"
                            :options="options"
                            class="custom-multiselect"
                            :searchable="false"
                            placeholder="Choose..."
                            selected-label=""
                            select-label=""
                            deselect-label=""
                        ></multiselect>
                    </div>
                    <template v-if="codeArr.includes('code4')">
                        <highlight>
                            <pre>
&lt;!-- placeholder --&gt;
&lt;multiselect v-model=&quot;input4&quot; :options=&quot;options&quot; class=&quot;custom-multiselect&quot; :searchable=&quot;false&quot; placeholder=&quot;Choose...&quot; selected-label=&quot;&quot; select-label=&quot;&quot; deselect-label=&quot;&quot;&gt;&lt;/multiselect&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref } from 'vue';
  import Multiselect from '@suadelabs/vue3-multiselect';
  import '@suadelabs/vue3-multiselect/dist/vue3-multiselect.css';

  const options = ref(['Orange', 'White', 'Purple']);
  const input4 = ref('');
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Searchable -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Searchable</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code5')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5">
                        <multiselect
                            v-model="input5"
                            :options="options"
                            class="custom-multiselect"
                            :searchable="true"
                            placeholder="Select an option"
                            selected-label=""
                            select-label=""
                            deselect-label=""
                        ></multiselect>
                    </div>
                    <template v-if="codeArr.includes('code5')">
                        <highlight>
                            <pre>
&lt;!-- searchable --&gt;
&lt;multiselect
  v-model=&quot;input5&quot;
  :options=&quot;options&quot;
  class=&quot;custom-multiselect&quot;
  :searchable=&quot;true&quot;
  placeholder=&quot;Select an option&quot;
  selected-label=&quot;&quot;
  select-label=&quot;&quot;
  deselect-label=&quot;&quot;
&gt;&lt;/multiselect&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref } from 'vue';
  import Multiselect from '@suadelabs/vue3-multiselect';
  import '@suadelabs/vue3-multiselect/dist/vue3-multiselect.css';

  const options = ref(['Orange', 'White', 'Purple']);
  const input5 = ref('');
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Multiple -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Multiple select</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code6')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5">
                        <multiselect
                            v-model="input6"
                            :options="options"
                            class="custom-multiselect"
                            :multiple="true"
                            :searchable="false"
                            placeholder="Select an option"
                            selected-label=""
                            select-label=""
                            deselect-label=""
                        >
                        </multiselect>
                    </div>
                    <template v-if="codeArr.includes('code6')">
                        <highlight>
                            <pre>
&lt;!-- multiple --&gt;
&lt;multiselect
  v-model=&quot;input6&quot;
  :options=&quot;options&quot;
  class=&quot;custom-multiselect&quot;
  :multiple=&quot;true&quot;
  :searchable=&quot;false&quot;
  placeholder=&quot;Select an option&quot;
  selected-label=&quot;&quot;
  select-label=&quot;&quot;
  deselect-label=&quot;&quot;
&gt;
&lt;/multiselect&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref } from 'vue';
  import Multiselect from '@suadelabs/vue3-multiselect';
  import '@suadelabs/vue3-multiselect/dist/vue3-multiselect.css';

  const options = ref(['Orange', 'White', 'Purple']);
  const input6 = ref([]);
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
    import Multiselect from '@suadelabs/vue3-multiselect';
    import '@suadelabs/vue3-multiselect/dist/vue3-multiselect.css';
    import { useMeta } from '@/composables/use-meta';

    import IconBell from '@/components/icon/icon-bell.vue';
    import IconCode from '@/components/icon/icon-code.vue';

    useMeta({ title: 'Vue Multiselect' });

    const { codeArr, toggleCode } = codePreview();

    const options = ref(['Orange', 'White', 'Purple']);
    const input1 = ref('Orange');

    const options2 = ref([
        {
            group_name: 'Group 1',
            list: [{ name: 'Orange' }, { name: 'White' }, { name: 'Purple' }],
        },
        {
            group_name: 'Group 2',
            list: [{ name: 'Yellow' }, { name: 'Red' }, { name: 'Green' }],
        },
        {
            group_name: 'Group 3',
            list: [{ name: 'Aqua' }, { name: 'Black' }, { name: 'Blue' }],
        },
    ]);
    const input2 = ref({ name: 'Orange' });

    const options3 = ref([{ name: 'Orange' }, { name: 'White', $isDisabled: true }, { name: 'Purple' }]);
    const input3 = ref({ name: 'Orange' });

    const input4 = ref('');
    const input5 = ref('');
    const input6 = ref([]);
</script>
