<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Forms</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Date and Range Picker</span>
            </li>
        </ul>
        <div class="pt-5 space-y-8">
            <div class="bg-[#009688]/[.26] text-[#009688] py-1 px-2 rounded inline-block text-base">Date and Time Picker</div>
            <div class="panel p-3 flex items-center text-primary overflow-x-auto whitespace-nowrap">
                <div class="ring-2 ring-primary/30 rounded-full bg-primary text-white p-1.5 ltr:mr-3 rtl:ml-3">
                    <icon-bell />
                </div>
                <span class="ltr:mr-3 rtl:ml-3">Documentation: </span
                ><a href="https://www.npmjs.com/package/vue-flatpickr-component" target="_blank" class="block hover:underline"
                    >https://www.npmjs.com/package/vue-flatpickr-component</a
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
                        <flat-pickr v-model="date1" class="form-input" :config="basic"></flat-pickr>
                    </div>
                    <template v-if="codeArr.includes('code1')">
                        <highlight>
                            <pre>
&lt;!-- basic --&gt;
&lt;flat-pickr v-model=&quot;date1&quot; class=&quot;form-input&quot; :config=&quot;basic&quot;&gt;&lt;/flat-pickr&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref, onMounted } from 'vue';
  import { useAppStore } from '@/stores/index';

  //flatpickr
  import flatPickr from 'vue-flatpickr-component';
  import 'flatpickr/dist/flatpickr.css';

  const store = useAppStore();

  const date1 = ref('2022-07-05');
  const basic: any = ref({
    dateFormat: 'Y-m-d',
    position: store.rtlClass === 'rtl' ? 'auto right' : 'auto left',
  });
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Date & time -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Date Time</h5>
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
                    <div class="mb-2.5">Use <code class="text-danger">{enableTime: true, dateFormat: 'Y-m-d H:i'}</code> option to enable time support</div>
                    <div class="mb-5">
                        <flat-pickr v-model="date2" class="form-input" :config="dateTime"></flat-pickr>
                    </div>
                    <template v-if="codeArr.includes('code2')">
                        <highlight>
                            <pre>
&lt;!-- date & time --&gt;
&lt;flat-pickr v-model=&quot;date2&quot; class=&quot;form-input&quot; :config=&quot;dateTime&quot;&gt;&lt;/flat-pickr&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref, onMounted } from 'vue';
  import { useAppStore } from '@/stores/index';

  //flatpickr
  import flatPickr from 'vue-flatpickr-component';
  import 'flatpickr/dist/flatpickr.css';

  const store = useAppStore();

  const date2 = ref('2022-07-05 12:00');
  const dateTime: any = ref({
    enableTime: true,
    dateFormat: 'Y-m-d H:i',
    position: store.rtlClass === 'rtl' ? 'auto right' : 'auto left',
  });
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- range-calendar -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Range Calendar</h5>
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
                    <div class="mb-2.5">Use <code class="text-danger">{mode: 'range'}</code> select the date with range.</div>
                    <div class="mb-5">
                        <flat-pickr v-model="date3" class="form-input" :config="rangeCalendar"></flat-pickr>
                    </div>
                    <template v-if="codeArr.includes('code3')">
                        <highlight>
                            <pre>
&lt;!-- range calendar --&gt;
&lt;flat-pickr v-model=&quot;date3&quot; class=&quot;form-input&quot; :config=&quot;rangeCalendar&quot;&gt;&lt;/flat-pickr&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref, onMounted } from 'vue';
  import { useAppStore } from '@/stores/index';

  //flatpickr
  import flatPickr from 'vue-flatpickr-component';
  import 'flatpickr/dist/flatpickr.css';

  const store = useAppStore();

  const date3 = ref('2022-07-05 to 2022-07-10');
  const rangeCalendar: any = ref({
    dateFormat: 'Y-m-d',
    mode: 'range',
    position: store.rtlClass === 'rtl' ? 'auto right' : 'auto left',
  });
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- preloading time -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Preloading Time</h5>
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
                    <div class="mb-2.5">
                        Use <code class="text-danger">{noCalendar: true, enableTime: true, dateFormat: 'H:i'}</code> with Date Time options to disable calendar
                        and show time picker only.
                    </div>
                    <div class="mb-5">
                        <flat-pickr v-model="date4" class="form-input" :config="preloadingTime"></flat-pickr>
                    </div>
                    <template v-if="codeArr.includes('code4')">
                        <highlight>
                            <pre>
&lt;!-- preloading time --&gt;
&lt;flat-pickr v-model=&quot;date4&quot; class=&quot;form-input&quot; :config=&quot;preloadingTime&quot;&gt;&lt;/flat-pickr&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref, onMounted } from 'vue';
  import { useAppStore } from '@/stores/index';

  //flatpickr
  import flatPickr from 'vue-flatpickr-component';
  import 'flatpickr/dist/flatpickr.css';

  const store = useAppStore();

  const date4 = ref('13:45');
  const preloadingTime: any = ref({
    noCalendar: true,
    enableTime: true,
    dateFormat: 'H:i',
    position: store.rtlClass === 'rtl' ? 'auto right' : 'auto left',
  });
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
            </div>

            <!-- range picker -->
            <div class="bg-[#009688]/[.26] text-[#009688] py-1 px-2 rounded inline-block text-base">Javascript Range Slider</div>
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                <!-- Top-Left -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Postion : Top-Left</h5>
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
                    <div class="mb-5 pt-5">
                        <div class="font-bold">
                            <span class="inline-block py-1 px-2 rounded text-primary border border-white-light dark:border-dark">{{ slider1 }}</span>
                            <span>%</span>
                        </div>
                        <input type="range" class="w-full py-2.5" min="0" max="100" v-model="slider1" />
                    </div>
                    <template v-if="codeArr.includes('code5')">
                        <highlight>
                            <pre>
&lt;!-- top left --&gt;
&lt;div&gt;
  &lt;div class=&quot;font-bold&quot;&gt;
    &lt;span class=&quot;inline-block py-1 px-2 rounded text-primary border border-white-light dark:border-dark&quot;&gt;{{ slider1 }}&lt;/span&gt;
    &lt;span&gt;%&lt;/span&gt;
  &lt;/div&gt;
  &lt;input type=&quot;range&quot; class=&quot;w-full py-2.5&quot; min=&quot;0&quot; max=&quot;100&quot; v-model=&quot;slider1&quot; /&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref, onMounted } from 'vue';
  const slider1 = ref(0);
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Top-right -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Postion : Top-right</h5>
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
                        <div class="font-bold ltr:text-right rtl:text-left">
                            <span class="inline-block py-1 px-2 rounded text-primary border border-white-light dark:border-dark">{{ slider2 }}</span>
                            <span>%</span>
                        </div>
                        <input type="range" class="w-full py-2.5" min="0" max="100" v-model="slider2" />
                    </div>
                    <template v-if="codeArr.includes('code6')">
                        <highlight>
                            <pre>
&lt;!-- top right --&gt;
&lt;div&gt;
  &lt;div class=&quot;font-bold ltr:text-right rtl:text-left&quot;&gt;
    &lt;span class=&quot;inline-block py-1 px-2 rounded text-primary border border-white-light dark:border-dark&quot;&gt;{{
                                    slider2
                                }}&lt;/span&gt; &lt;span&gt;%&lt;/span&gt;
  &lt;/div&gt;
  &lt;input type=&quot;range&quot; class=&quot;w-full py-2.5&quot; min=&quot;0&quot; max=&quot;100&quot; v-model=&quot;slider2&quot; /&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref, onMounted } from 'vue';
  const slider2 = ref(0);
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- bottom-left -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Postion : Bottom-Left</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code7')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5">
                        <input type="range" class="w-full py-2.5" min="0" max="100" v-model="slider3" />
                        <div class="font-bold">
                            <span class="inline-block py-1 px-2 rounded text-primary border border-white-light dark:border-dark">{{ slider3 }}</span>
                            <span>%</span>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code7')">
                        <highlight>
                            <pre>
&lt;!-- bottom left --&gt;
&lt;div&gt;
  &lt;input type=&quot;range&quot; class=&quot;w-full py-2.5&quot; min=&quot;0&quot; max=&quot;100&quot; v-model=&quot;slider3&quot; /&gt;
  &lt;div class=&quot;font-bold&quot;&gt;
    &lt;span class=&quot;inline-block py-1 px-2 rounded text-primary border border-white-light dark:border-dark&quot;&gt;{{
                                    slider3
                                }}&lt;/span&gt; &lt;span&gt;%&lt;/span&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref, onMounted } from 'vue';
  const slider3 = ref(0);
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Bottom-right -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Postion : Bottom-right</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code8')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5">
                        <input type="range" class="w-full py-2.5" min="0" max="100" v-model="slider4" />
                        <div class="font-bold ltr:text-right rtl:text-left">
                            <span class="inline-block py-1 px-2 rounded text-primary border border-white-light dark:border-dark">{{ slider4 }}</span>
                            <span>%</span>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code8')">
                        <highlight>
                            <pre>
&lt;!-- bottom right --&gt;
&lt;div&gt;
  &lt;input type=&quot;range&quot; class=&quot;w-full py-2.5&quot; min=&quot;0&quot; max=&quot;100&quot; v-model=&quot;slider4&quot; /&gt;
  &lt;div class=&quot;font-bold ltr:text-right rtl:text-left&quot;&gt;
    &lt;span class=&quot;inline-block py-1 px-2 rounded text-primary border border-white-light dark:border-dark&quot;&gt;{{
                                    slider4
                                }}&lt;/span&gt; &lt;span&gt;%&lt;/span&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref, onMounted } from 'vue';
  const slider4 = ref(0);
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
            </div>

            <!-- Nouislider -->
            <div class="bg-[#009688]/[.26] text-[#009688] py-1 px-2 rounded inline-block text-base">noUI Slider</div>

            <div class="panel p-3 flex items-center text-primary overflow-x-auto whitespace-nowrap">
                <div class="ring-2 ring-primary/30 rounded-full bg-primary text-white p-1.5 ltr:mr-3 rtl:ml-3">
                    <icon-bell />
                </div>
                <span class="ltr:mr-3 rtl:ml-3">Documentation: </span
                ><a href="https://www.npmjs.com/package/vue-simple-range-slider" target="_blank" class="block hover:underline"
                    >https://www.npmjs.com/package/vue-simple-range-slider</a
                >
            </div>
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-6 range-slider">
                <!-- Using HTML5 input elements -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Using HTML5 input elements</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code10')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5 pt-5">
                        <VueSimpleRangeSlider
                            style="width: 100%"
                            :min="0"
                            :max="100"
                            v-model="nouiSlider1"
                            :update="slider1Update(nouiSlider1)"
                            :bar-color="store.theme === 'dark' || store.isDarkMode ? '#1b2e4b' : '#ffffff'"
                            active-bar-color="#4361ee"
                        ></VueSimpleRangeSlider>
                        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 my-4">
                            <div class="mb-3">
                                <select v-model="nouiMin1" class="form-select w-full" id="select" @change="selectUpdateValue()">
                                    <template v-for="(i, index) in 100" :key="i">
                                        <option>{{ index }}</option>
                                    </template>
                                </select>
                            </div>
                            <div>
                                <input type="number" v-model="nouiMax1" class="form-input" :min="-20" :max="100" step="1" @blur="selectUpdateValue()" />
                            </div>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code10')">
                        <highlight>
                            <pre>
&lt;!-- using HTML5 input elements --&gt;
&lt;VueSimpleRangeSlider
  style=&quot;width: 100%&quot;
  :min=&quot;0&quot;
  :max=&quot;100&quot;
  v-model=&quot;nouiSlider1&quot;
  :update=&quot;slider1Update(nouiSlider1)&quot;
  :bar-color=&quot;store.theme === 'dark' || store.isDarkMode ? '#1b2e4b' : '#ffffff'&quot;
  active-bar-color=&quot;#4361ee&quot;
&gt;&lt;/VueSimpleRangeSlider&gt;
&lt;div class=&quot;grid grid-cols-1 lg:grid-cols-2 gap-8 my-4&quot;&gt;
  &lt;div class=&quot;mb-3&quot;&gt;
    &lt;select v-model=&quot;nouiMin1&quot; class=&quot;form-select w-full&quot; id=&quot;select&quot; @change=&quot;selectUpdateValue()&quot;&gt;
      &lt;template v-for=&quot;(i, index) in 61&quot; :key=&quot;i&quot;&gt;
        &lt;option&gt;&#123;&#123; index &#125;&#125;&lt;/option&gt;
      &lt;/template&gt;
    &lt;/select&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;input type=&quot;number&quot; v-model=&quot;nouiMax1&quot; class=&quot;form-input&quot; :min=&quot;-20&quot; :max=&quot;100&quot; step=&quot;1&quot; @blur=&quot;selectUpdateValue()&quot; /&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref, onMounted } from 'vue';
  // range slider
  import VueSimpleRangeSlider from 'vue-simple-range-slider';
  import 'vue-simple-range-slider/css';

  const nouiMin1 = ref(20);
  const nouiMax1 = ref(40);
  const nouiSlider1: any = ref([nouiMin1.value, nouiMax1.value]);

  const slider1Update = (range) =&gt; {
    if (range) {
      nouiMin1.value = range[0];
      nouiMax1.value = JSON.parse(JSON.stringify(range[1]));
    }
  };
  const selectUpdateValue = () =&gt; {
    nouiSlider1.value = [nouiMin1.value, nouiMax1.value];
  };
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Non linear slider -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Non linear slider</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code11')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5 pt-5">
                        <VueSimpleRangeSlider
                            style="width: 100%"
                            :min="0"
                            :max="10000"
                            v-model="nouiSlider2"
                            :bar-color="store.theme === 'dark' || store.isDarkMode ? '#1b2e4b' : '#ffffff'"
                            active-bar-color="#4361ee"
                            :update="slider2Update(nouiSlider2)"
                        >
                        </VueSimpleRangeSlider>

                        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 my-5 font-bold">
                            <div>
                                <span class="text-primary mr-2" id="nouiMin2">{{ parseInt(nouiSlider2[0]).toFixed(2) }}</span
                                ><span class="border border-white-light dark:border-dark py-1 px-2 text-dark dark:text-white-dark rounded" id="nouiMin2Perc"
                                    >{{ nouiMin2Perc }}%</span
                                >
                            </div>
                            <div class="ltr:text-right rtl:text-left">
                                <span class="text-primary mr-2" id="nouiMax2">{{ parseInt(nouiSlider2[1]).toFixed(2) }}</span
                                ><span class="border border-white-light dark:border-dark py-1 px-2 text-dark dark:text-white-dark rounded" id="nouiMax2Perc"
                                    >{{ nouiMax2Perc }}%</span
                                >
                            </div>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code11')">
                        <highlight>
                            <pre>
&lt;!-- non linear slider --&gt;
&lt;VueSimpleRangeSlider
  style=&quot;width: 100%&quot;
  :min=&quot;0&quot;
  :max=&quot;10000&quot;
  v-model=&quot;nouiSlider2&quot;
  :bar-color=&quot;store.theme === 'dark' || store.isDarkMode ? '#1b2e4b' : '#ffffff'&quot;
  active-bar-color=&quot;#4361ee&quot;
  :update=&quot;slider2Update(nouiSlider2)&quot;
&gt;
&lt;/VueSimpleRangeSlider&gt;

&lt;div class=&quot;grid grid-cols-1 lg:grid-cols-2 gap-8 my-5 font-bold&quot;&gt;
  &lt;div&gt;
    &lt;span class=&quot;text-primary mr-2&quot; id=&quot;nouiMin2&quot;&gt;{{ parseInt(nouiSlider2[0]).toFixed(2) }}&lt;/span
    &gt;&lt;span class=&quot;border border-white-light dark:border-dark py-1 px-2 text-dark dark:text-white-dark rounded&quot; id=&quot;nouiMin2Perc&quot;&gt;{{
                                    nouiMin2Perc
                                }}%&lt;/span&gt;
  &lt;/div&gt;
  &lt;div class=&quot;ltr:text-right rtl:text-left&quot;&gt;
    &lt;span class=&quot;text-primary mr-2&quot; id=&quot;nouiMax2&quot;&gt;{{ parseInt(nouiSlider2[1]).toFixed(2) }}&lt;/span
    &gt;&lt;span class=&quot;border border-white-light dark:border-dark py-1 px-2 text-dark dark:text-white-dark rounded&quot; id=&quot;nouiMax2Perc&quot;&gt;{{
                                    nouiMax2Perc
                                }}%&lt;/span&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref, onMounted } from 'vue';
  // range slider
  import VueSimpleRangeSlider from 'vue-simple-range-slider';
  import 'vue-simple-range-slider/css';

  const nouiSlider2: any = ref([500, 4000]);
  const nouiMin2Perc = ref(0);
  const nouiMax2Perc = ref(0);

  const slider2Update = (range) =&gt; {
    if (range) {
      nouiMin2Perc.value = parseFloat((range[0] * 0.01).toFixed(2));
      nouiMax2Perc.value = parseFloat((range[1] * 0.01).toFixed(2));
    }
  };
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Locking slider -->
                <div class="panel lg:col-span-2">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Locking sliders together</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code12')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5 pt-5">
                        <VueSimpleRangeSlider
                            style="width: 100%"
                            :min="0"
                            :max="100"
                            v-model="nouiSlider3"
                            :bar-color="store.theme === 'dark' || store.isDarkMode ? '#1b2e4b' : '#ffffff'"
                            active-bar-color="#4361ee"
                            :update="setLockSlider1()"
                        >
                        </VueSimpleRangeSlider>
                        <div class="text-primary font-bold mb-10" id="locking_slider1_value"></div>
                        <VueSimpleRangeSlider
                            style="width: 100%"
                            :min="0"
                            v-model="nouiSlider4"
                            :bar-color="store.theme === 'dark' || store.isDarkMode ? '#1b2e4b' : '#ffffff'"
                            active-bar-color="#4361ee"
                        >
                        </VueSimpleRangeSlider>
                        <div class="text-primary font-bold mb-10" id="locking_slider2_value"></div>
                        <div class="ltr:text-right rtl:text-left">
                            <button type="button" class="btn btn-primary" id="lockbutton" @click="setLock">{{ lockedState ? 'Unlock' : 'Lock' }}</button>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code12')">
                        <highlight>
                            <pre>
&lt;!-- locking sliders together --&gt;
&lt;VueSimpleRangeSlider
  style=&quot;width: 100%&quot;
  :min=&quot;0&quot;
  :max=&quot;100&quot;
  v-model=&quot;nouiSlider3&quot;
  :bar-color=&quot;store.theme === 'dark' || store.isDarkMode || store.isDarkMode ? '#1b2e4b' : '#ffffff'&quot;
  active-bar-color=&quot;#4361ee&quot;
  :update=&quot;setLockSlider1()&quot;
&gt;
&lt;/VueSimpleRangeSlider&gt;
&lt;div class=&quot;text-primary font-bold mb-10&quot; id=&quot;locking_slider1_value&quot;&gt;&lt;/div&gt;
&lt;VueSimpleRangeSlider style=&quot;width: 100%&quot; :min=&quot;0&quot; v-model=&quot;nouiSlider4&quot; :bar-color=&quot;store.theme === 'dark' || store.isDarkMode ? '#1b2e4b' : '#ffffff'&quot; active-bar-color=&quot;#4361ee&quot;&gt; &lt;/VueSimpleRangeSlider&gt;
&lt;div class=&quot;text-primary font-bold mb-10&quot; id=&quot;locking_slider2_value&quot;&gt;&lt;/div&gt;
&lt;div class=&quot;ltr:text-right rtl:text-left&quot;&gt;
  &lt;button type=&quot;button&quot; class=&quot;btn btn-primary&quot; id=&quot;lockbutton&quot; @click=&quot;setLock&quot;&gt;{{
                                    lockedState ? 'Unlock' : 'Lock'
                                }}&lt;/button&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
  import { ref, onMounted } from 'vue';
  // range slider
  import VueSimpleRangeSlider from 'vue-simple-range-slider';
  import 'vue-simple-range-slider/css';

  onMounted(() =&gt; {
    setLock();
  });

  const nouiSlider3: any = ref(5);
  const nouiSlider4: any = ref(10);
  const lockedState = ref(false);
  const lockingSlider1 = ref(0);
  const lockingSlider2 = ref(0);

  const setLock = () =&gt; {
    lockedState.value = !lockedState.value;
    if (lockedState.value) {
      lockingSlider1.value = nouiSlider3.value;
      lockingSlider2.value = nouiSlider4.value;
    }
  };

  const setLockSlider1 = () =&gt; {
    if (!lockedState.value) {
      return false;
    }

    if (lockingSlider1.value &gt; lockingSlider2.value) {
      nouiSlider4.value = nouiSlider3.value - lockingSlider1.value;
    } else if (lockingSlider1.value &lt; lockingSlider2.value) {
      nouiSlider4.value = lockingSlider1.value + nouiSlider3.value;
    } else {
      nouiSlider4.value = nouiSlider3.value;
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
    </div>
</template>
<script lang="ts" setup>
    import { ref, onMounted } from 'vue';
    import highlight from '@/components/plugins/highlight.vue';
    import codePreview from '@/composables/codePreview';
    import { useAppStore } from '@/stores/index';

    //flatpickr
    import flatPickr from 'vue-flatpickr-component';
    import 'flatpickr/dist/flatpickr.css';
    // range slider
    import VueSimpleRangeSlider from 'vue-simple-range-slider';
    import 'vue-simple-range-slider/css';

    import { useMeta } from '@/composables/use-meta';

    import IconBell from '@/components/icon/icon-bell.vue';
    import IconCode from '@/components/icon/icon-code.vue';

    useMeta({ title: 'Date & Range Picker' });

    const store = useAppStore();

    const { codeArr, toggleCode } = codePreview();

    const date1 = ref('2022-07-05');
    const basic: any = ref({
        dateFormat: 'Y-m-d',
        position: store.rtlClass === 'rtl' ? 'auto right' : 'auto left',
    });

    const date2 = ref('2022-07-05 12:00');
    const dateTime: any = ref({
        enableTime: true,
        dateFormat: 'Y-m-d H:i',
        position: store.rtlClass === 'rtl' ? 'auto right' : 'auto left',
    });

    const date3 = ref('2022-07-05 to 2022-07-10');
    const rangeCalendar: any = ref({
        dateFormat: 'Y-m-d',
        mode: 'range',
        position: store.rtlClass === 'rtl' ? 'auto right' : 'auto left',
    });

    const date4 = ref('13:45');
    const preloadingTime: any = ref({
        noCalendar: true,
        enableTime: true,
        dateFormat: 'H:i',
        position: store.rtlClass === 'rtl' ? 'auto right' : 'auto left',
    });

    const slider1 = ref(0);
    const slider2 = ref(0);
    const slider3 = ref(0);
    const slider4 = ref(0);

    const nouiMin1 = ref(20);
    const nouiMax1 = ref(40);
    const nouiSlider1: any = ref([nouiMin1.value, nouiMax1.value]);

    const nouiSlider2: any = ref([500, 4000]);
    const nouiMin2Perc = ref(0);
    const nouiMax2Perc = ref(0);

    onMounted(() => {
        setLock();
    });

    const slider1Update = (range) => {
        if (range) {
            nouiMin1.value = range[0];
            nouiMax1.value = JSON.parse(JSON.stringify(range[1]));
        }
    };
    const slider2Update = (range) => {
        if (range) {
            nouiMin2Perc.value = parseFloat((range[0] * 0.01).toFixed(2));
            nouiMax2Perc.value = parseFloat((range[1] * 0.01).toFixed(2));
        }
    };
    const selectUpdateValue = () => {
        nouiSlider1.value = [nouiMin1.value, nouiMax1.value];
    };

    const nouiSlider3: any = ref(5);
    const nouiSlider4: any = ref(10);
    const lockedState = ref(false);
    const lockingSlider1 = ref(0);
    const lockingSlider2 = ref(0);

    const setLock = () => {
        lockedState.value = !lockedState.value;
        if (lockedState.value) {
            lockingSlider1.value = nouiSlider3.value;
            lockingSlider2.value = nouiSlider4.value;
        }
    };

    const setLockSlider1 = () => {
        if (!lockedState.value) {
            return false;
        }

        if (lockingSlider1.value > lockingSlider2.value) {
            nouiSlider4.value = nouiSlider3.value - lockingSlider1.value;
        } else if (lockingSlider1.value < lockingSlider2.value) {
            nouiSlider4.value = lockingSlider1.value + nouiSlider3.value;
        } else {
            nouiSlider4.value = nouiSlider3.value;
        }
    };
</script>
