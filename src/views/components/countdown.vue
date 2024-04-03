<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Components</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Countdown</span>
            </li>
        </ul>
        <div class="pt-5 grid grid-cols-1 xl:grid-cols-2 gap-6">
            <!-- Simple Countdown -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Simple Countdown</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code1')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5 grid grid-cols-4 justify-items-center gap-3">
                    <div>
                        <div
                            class="w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                        >
                            <h1 class="text-primary sm:text-3xl text-xl text-center">{{ demo1.days }}</h1>
                        </div>
                        <h4 class="text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold">Days</h4>
                    </div>
                    <div>
                        <div
                            class="w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                        >
                            <h1 class="text-primary sm:text-3xl text-xl text-center">{{ demo1.hours }}</h1>
                        </div>
                        <h4 class="text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold">Hours</h4>
                    </div>
                    <div>
                        <div
                            class="w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                        >
                            <h1 class="text-primary sm:text-3xl text-xl text-center">{{ demo1.minutes }}</h1>
                        </div>
                        <h4 class="text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold">Mins</h4>
                    </div>
                    <div>
                        <div
                            class="w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                        >
                            <h1 class="text-primary sm:text-3xl text-xl text-center">{{ demo1.seconds }}</h1>
                        </div>
                        <h4 class="text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold">Sec</h4>
                    </div>
                </div>
                <template v-if="codeArr.includes('code1')">
                    <highlight>
                        <pre>
&lt;!-- simple countdown --&gt;
&lt;div class=&quot;mb-5 grid grid-cols-4 justify-items-center gap-3&quot;&gt;
  &lt;div&gt;
    &lt;div class=&quot;w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;&gt;
      &lt;h1 class=&quot;text-primary sm:text-3xl text-xl text-center&quot;&gt;&#123;&#123; demo1.days &#125;&#125;&lt;/h1&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;Days&lt;/h4&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div class=&quot;w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;&gt;
      &lt;h1 class=&quot;text-primary sm:text-3xl text-xl text-center&quot;&gt;&#123;&#123; demo1.hours &#125;&#125;&lt;/h1&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;Hours&lt;/h4&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div class=&quot;w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;&gt;
      &lt;h1 class=&quot;text-primary sm:text-3xl text-xl text-center&quot;&gt;&#123;&#123; demo1.minutes &#125;&#125;&lt;/h1&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;Mins&lt;/h4&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div class=&quot;w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;&gt;
      &lt;h1 class=&quot;text-primary sm:text-3xl text-xl text-center&quot;&gt;&#123;&#123; demo1.seconds &#125;&#125;&lt;/h1&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;Sec&lt;/h4&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref, onMounted } from 'vue';
const timer1: any = ref(null);
const demo1: any = ref({
  days: null,
  hours: null,
  minutes: null,
  seconds: null,
});

onMounted(() =&gt; {
  setTimerDemo1();
});

const setTimerDemo1 = () =&gt; {
  let date = new Date();
  date.setDate(date.getDate() + 3);
  let countDownDate = date.getTime();

  timer1.value = setInterval(() =&gt; {
    let now = new Date().getTime();

    let distance = countDownDate - now;

    demo1.value.days = Math.floor(distance / (1000 * 60 * 60 * 24));
    demo1.value.hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    demo1.value.minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    demo1.value.seconds = Math.floor((distance % (1000 * 60)) / 1000);

    if (distance &lt; 0) {
      clearInterval(timer1.value);
    }
  }, 500);
};
&lt;/script&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Circle Countdown -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Circle Countdown</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code2')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5 grid grid-cols-4 justify-items-center gap-3">
                    <div>
                        <div
                            class="w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                        >
                            <h1 class="text-primary sm:text-3xl text-xl text-center">{{ demo2.days }}</h1>
                        </div>
                        <h4 class="text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold">Days</h4>
                    </div>
                    <div>
                        <div
                            class="w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                        >
                            <h1 class="text-primary sm:text-3xl text-xl text-center">{{ demo2.hours }}</h1>
                        </div>
                        <h4 class="text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold">Hours</h4>
                    </div>
                    <div>
                        <div
                            class="w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                        >
                            <h1 class="text-primary sm:text-3xl text-xl text-center">{{ demo2.minutes }}</h1>
                        </div>
                        <h4 class="text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold">Mins</h4>
                    </div>
                    <div>
                        <div
                            class="w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col"
                        >
                            <h1 class="text-primary sm:text-3xl text-xl text-center">{{ demo2.seconds }}</h1>
                        </div>
                        <h4 class="text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold">Sec</h4>
                    </div>
                </div>
                <template v-if="codeArr.includes('code2')">
                    <highlight>
                        <pre>
&lt;!-- circle countdown --&gt;
&lt;div class=&quot;mb-5 grid grid-cols-4 justify-items-center gap-3&quot;&gt;
  &lt;div&gt;
    &lt;div class=&quot;w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;&gt;
      &lt;h1 class=&quot;text-primary sm:text-3xl text-xl text-center&quot;&gt;&#123;&#123; demo2.days &#125;&#125;&lt;/h1&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;Days&lt;/h4&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div class=&quot;w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;&gt;
      &lt;h1 class=&quot;text-primary sm:text-3xl text-xl text-center&quot;&gt;&#123;&#123; demo2.hours &#125;&#125;&lt;/h1&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;Hours&lt;/h4&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div class=&quot;w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;&gt;
      &lt;h1 class=&quot;text-primary sm:text-3xl text-xl text-center&quot;&gt;&#123;&#123; demo2.minutes &#125;&#125;&lt;/h1&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;Mins&lt;/h4&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div class=&quot;w-16 h-16 sm:w-[100px] sm:h-[100px] shadow-[1px_2px_12px_0_rgba(31,45,61,0.10)] rounded-full border border-[#e0e6ed] dark:border-[#1b2e4b] flex justify-center flex-col&quot;&gt;
      &lt;h1 class=&quot;text-primary sm:text-3xl text-xl text-center&quot;&gt;&#123;&#123; demo2.seconds &#125;&#125;&lt;/h1&gt;
    &lt;/div&gt;
    &lt;h4 class=&quot;text-[#3b3f5c] text-[15px] mt-4 text-center dark:text-white-dark font-semibold&quot;&gt;Sec&lt;/h4&gt;
  &lt;/div&gt;
&lt;/div&gt;
&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref, onMounted } from 'vue';
const timer2: any = ref(null);
const demo2: any = ref({
  days: null,
  hours: null,
  minutes: null,
  seconds: null,
});

onMounted(() =&gt; {
  setTimerDemo2();
});

const setTimerDemo2 = () =&gt; {
  let date = new Date();
  date.setFullYear(date.getFullYear() + 1);
  let countDownDate = date.getTime();

  timer2.value = setInterval(() =&gt; {
    let now = new Date().getTime();

    let distance = countDownDate - now;

    demo2.value.days = Math.floor(distance / (1000 * 60 * 60 * 24));
    demo2.value.hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    demo2.value.minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    demo2.value.seconds = Math.floor((distance % (1000 * 60)) / 1000);

    if (distance &lt; 0) {
      clearInterval(timer2.value);
    }
  }, 500);
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
    import { ref, onMounted } from 'vue';
    import highlight from '@/components/plugins/highlight.vue';
    import codePreview from '@/composables/codePreview';
    import { useMeta } from '@/composables/use-meta';

    import IconCode from '@/components/icon/icon-code.vue';

    useMeta({ title: 'Countdown' });

    const { codeArr, toggleCode } = codePreview();

    const timer1: any = ref(null);
    const demo1: any = ref({
        days: null,
        hours: null,
        minutes: null,
        seconds: null,
    });
    const timer2: any = ref(null);
    const demo2: any = ref({
        days: null,
        hours: null,
        minutes: null,
        seconds: null,
    });

    onMounted(() => {
        setTimerDemo1();
        setTimerDemo2();
    });

    const setTimerDemo1 = () => {
        let date = new Date();
        date.setDate(date.getDate() + 3);
        let countDownDate = date.getTime();

        timer1.value = setInterval(() => {
            let now = new Date().getTime();

            let distance = countDownDate - now;

            demo1.value.days = Math.floor(distance / (1000 * 60 * 60 * 24));
            demo1.value.hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            demo1.value.minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            demo1.value.seconds = Math.floor((distance % (1000 * 60)) / 1000);

            if (distance < 0) {
                clearInterval(timer1.value);
            }
        }, 500);
    };

    const setTimerDemo2 = () => {
        let date = new Date();
        date.setFullYear(date.getFullYear() + 1);
        let countDownDate = date.getTime();

        timer2.value = setInterval(() => {
            let now = new Date().getTime();

            let distance = countDownDate - now;

            demo2.value.days = Math.floor(distance / (1000 * 60 * 60 * 24));
            demo2.value.hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            demo2.value.minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            demo2.value.seconds = Math.floor((distance % (1000 * 60)) / 1000);

            if (distance < 0) {
                clearInterval(timer2.value);
            }
        }, 500);
    };
</script>
