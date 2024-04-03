<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Components</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Notifications</span>
            </li>
        </ul>
        <div class="pt-5 space-y-8">
            <div class="panel p-3 flex items-center text-primary overflow-x-auto whitespace-nowrap">
                <div class="ring-2 ring-primary/30 rounded-full bg-primary text-white p-1.5 ltr:mr-3 rtl:ml-3">
                    <icon-bell />
                </div>
                <span class="ltr:mr-3 rtl:ml-3">Documentation: </span
                ><a href="https://www.npmjs.com/package/sweetalert2" target="_blank" class="block hover:underline">https://www.npmjs.com/package/sweetalert2</a>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                <!-- basic -->
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
                        <div class="flex items-center justify-center">
                            <button type="button" class="btn btn-primary" @click="showMessage('Hello, world! This is a toast message.')">Open Toast</button>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code1')">
                        <highlight>
                            <pre>
&lt;!-- basic --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-primary&quot; @click=&quot;showMessage('Hello, world! This is a toast message.')&quot;&gt;Open Toast&lt;/button&gt;

&lt;!-- script --&gt;
&lt;script&gt;
    const showMessage = (msg = 'Example notification text.', position = 'bottom-start', showCloseButton = true, closeButtonHtml = '', duration = 3000) =&gt; {
        const toast = Swal.mixin({
            toast: true,
            position: position || 'bottom-start',
            showConfirmButton: false,
            timer: duration,
            showCloseButton: showCloseButton,
        });
        toast.fire({
            title: msg,
        });
    };
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
                <!-- Position -->
                <div class="panel lg:row-span-2">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Position</h5>
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
                        <h6 class="font-semibold text-base dark:text-white-light mb-3 text-center">Top Position</h6>
                        <div class="flex items-center justify-center mb-10 gap-2">
                            <button
                                type="button"
                                class="btn btn-success"
                                @click="showMessage('Example notification text.', store.rtlClass === 'rtl' ? 'top-end' : 'top-start')"
                            >
                                Top Left
                            </button>
                            <button type="button" class="btn btn-secondary" @click="showMessage('Example notification text', 'top')">Top Center</button>
                            <button
                                type="button"
                                class="btn btn-info"
                                @click="showMessage('Example notification text.', store.rtlClass === 'rtl' ? 'top-start' : 'top-end')"
                            >
                                Top Right
                            </button>
                        </div>
                        <h6 class="font-semibold text-base dark:text-white-light mb-3 text-center">Bottom Position</h6>
                        <div class="flex items-center justify-center gap-2">
                            <button
                                type="button"
                                class="btn btn-dark"
                                @click="showMessage('Example notification text.', store.rtlClass === 'rtl' ? 'bottom-end' : 'bottom-start')"
                            >
                                Bottom Left
                            </button>
                            <button type="button" class="btn btn-primary" @click="showMessage('Example notification text.', 'bottom')">Bottom Center</button>
                            <button
                                type="button"
                                class="btn btn-secondary"
                                @click="showMessage('Example notification text.', store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end')"
                            >
                                Bottom Right
                            </button>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code2')">
                        <highlight>
                            <pre>
&lt;!-- top left --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-success&quot; @click=&quot;showMessage('Example notification text.',store.rtlClass === 'rtl' ? 'top-end' : 'top-start')&quot;&gt;Top Left&lt;/button&gt;

&lt;!-- top center --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-secondary&quot; @click=&quot;showMessage('Example notification text','top')&quot;&gt;Top Center&lt;/button&gt;

&lt;!-- top right --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-info&quot; @click=&quot;showMessage('Example notification text.', store.rtlClass === 'rtl' ? 'top-start' : 'top-end')&quot;&gt;Top Right&lt;/button&gt;

&lt;!-- bottom left --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-dark&quot; @click=&quot;showMessage('Example notification text.',store.rtlClass === 'rtl' ? 'bottom-end' : 'bottom-start')&quot;&gt;Bottom Left&lt;/button&gt;

&lt;!-- bottom center --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-primary&quot; @click=&quot;showMessage('Example notification text.','bottom')&quot;&gt;Bottom Center&lt;/button&gt;

&lt;!-- bottom right --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-secondary&quot; @click=&quot;showMessage('Example notification text.',store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end')&quot;&gt;Bottom Right&lt;/button&gt;

&lt;!-- script --&gt;
&lt;script&gt;
  import { useAppStore } from '@/stores/index';
  const store = useAppStore();
  const showMessage = (msg = 'Example notification text.', position = 'bottom-start', showCloseButton = true, closeButtonHtml = '', duration = 3000) =&gt; {
      const toast = Swal.mixin({
          toast: true,
          position: position || 'bottom-start',
          showConfirmButton: false,
          timer: duration,
          showCloseButton: showCloseButton,
      });
      toast.fire({
          title: msg,
      });
  };
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
                <!-- No Action -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">No Action</h5>
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
                        <div class="flex items-center justify-center">
                            <button type="button" class="btn btn-success" @click="showMessage('Example notification text.', 'bottom-start', false)">
                                No Action
                            </button>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code3')">
                        <highlight>
                            <pre>
&lt;!-- no action --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-success&quot; @click=&quot;showMessage('Example notification text.', 'bottom-start',false)&quot;&gt;No Action&lt;/button&gt;

&lt;!-- script --&gt;
&lt;script&gt;
    const showMessage = (msg = 'Example notification text.', position = 'bottom-start', showCloseButton = true, closeButtonHtml = '', duration = 3000) =&gt; {
        const toast = Swal.mixin({
            toast: true,
            position: position || 'bottom-start',
            showConfirmButton: false,
            timer: duration,
            showCloseButton: showCloseButton,
        });
        toast.fire({
            title: msg,
        });
    };
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Click Callback -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Click Callback</h5>
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
                        <div class="flex items-center justify-center">
                            <button type="button" class="btn btn-info" @click="clickCallable()">Click Callback</button>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code4')">
                        <highlight>
                            <pre>
&lt;!-- click callback --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-info&quot; @click=&quot;clickCallable()&quot;&gt;Click Callback&lt;/button&gt;

&lt;!-- script --&gt;
&lt;script&gt;
    const clickCallable = () =&gt; {
        Swal.fire({
            toast: true,
            position: 'bottom-start',
            text: &quot;Custom callback when action button is clicked.&quot;,
            showCloseButton: true,
            showConfirmButton: false,
        }).then((result) =&gt; {
            Swal.fire({
                toast: true,
                position: 'bottom-start',
                text: 'Thanks for clicking the Dismiss button!',
                showCloseButton: true,
                showConfirmButton: false,
            });
        });
    };
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
                <!-- Duration -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Duration</h5>
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
                        <div class="flex items-center justify-center">
                            <button
                                type="button"
                                class="btn btn-dark"
                                @click="showMessage((msg = 'Example notification text.'), (position = 'bottom-start'), (duration = 5000))"
                            >
                                Duration
                            </button>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code5')">
                        <highlight>
                            <pre>
&lt;!-- click callback --&gt;
&lt;button type=&quot;button&quot; class=&quot;btn btn-dark&quot; @click=&quot;showMessage(msg='Example notification text.', position= 'bottom-start', duration=5000)&quot;&gt;Duration&lt;/button&gt;

&lt;!-- script --&gt;
&lt;script&gt;
    const showMessage = (msg = 'Example notification text.', position = 'bottom-start', showCloseButton = true, closeButtonHtml = '', duration = 3000) =&gt; {
        const toast = Swal.mixin({
            toast: true,
            position: position || 'bottom-start',
            showConfirmButton: false,
            timer: duration,
            showCloseButton: showCloseButton,
        });
        toast.fire({
            title: msg,
        });
    };
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
                <!-- Background Color -->
                <div class="panel lg:col-span-2">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Background Color</h5>
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
                        <div class="grid grid-cols-2 sm:grid-cols-1 sm:flex items-center justify-center gap-2 colored-toast">
                            <div>
                                <button type="button" class="btn btn-primary" @click="coloredToast('primary')">Primary</button>
                                <div id="primary-toast"></div>
                            </div>
                            <div>
                                <button type="button" class="btn btn-secondary" @click="coloredToast('secondary')">Secondary</button>
                                <div id="secondary-toast"></div>
                            </div>
                            <div>
                                <button type="button" class="btn btn-success" @click="coloredToast('success')">Success</button>
                                <div id="success-toast"></div>
                            </div>
                            <div>
                                <button type="button" class="btn btn-danger" @click="coloredToast('danger')">Danger</button>
                                <div id="danger-toast"></div>
                            </div>
                            <div>
                                <button type="button" class="btn btn-warning" @click="coloredToast('warning')">Warning</button>
                                <div id="warning-toast"></div>
                            </div>
                            <div>
                                <button type="button" class="btn btn-info" @click="coloredToast('info')">Info</button>
                                <div id="info-toast"></div>
                            </div>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code6')">
                        <highlight>
                            <pre>
&lt;!-- primary --&gt;
&lt;div&gt;
    &lt;button type=&quot;button&quot; class=&quot;btn btn-primary&quot; @click=&quot;coloredToast('primary')&quot;&gt;Primary&lt;/button&gt;
    &lt;div id=&quot;primary-toast&quot;&gt;&lt;/div&gt;
&lt;/div&gt;

&lt;!-- secondary --&gt;
&lt;div&gt;
    &lt;button type=&quot; button&quot; class=&quot;btn btn-secondary&quot; @click=&quot;coloredToast('secondary')&quot;&gt;Secondary&lt;/button&gt;
    &lt;div id=&quot;secondary-toast&quot;&gt;&lt;/div&gt;
&lt;/div&gt;

&lt;!-- success --&gt;
&lt;div&gt;
    &lt;button type=&quot;button&quot; class=&quot;btn btn-success&quot; @click=&quot;coloredToast('success')&quot;&gt;Success&lt;/button&gt;
    &lt;div id=&quot;success-toast&quot;&gt;&lt;/div&gt;
&lt;/div&gt;

&lt;!-- danger --&gt;
&lt;div&gt;
    &lt;button type=&quot;button&quot; class=&quot;btn btn-danger&quot; @click=&quot;coloredToast('danger')&quot;&gt;Danger&lt;/button&gt;
    &lt;div id=&quot;danger-toast&quot;&gt;&lt;/div&gt;
&lt;/div&gt;

&lt;!-- warning --&gt;
&lt;div&gt;
    &lt;button type=&quot;button&quot; class=&quot;btn btn-warning&quot; @click=&quot;coloredToast('warning')&quot;&gt;Warning&lt;/button&gt;
    &lt;div id=&quot;warning-toast&quot;&gt;&lt;/div&gt;
&lt;/div&gt;

&lt;!-- info --&gt;
&lt;div&gt;
    &lt;button type=&quot;button&quot; class=&quot;btn btn-info&quot; @click=&quot;coloredToast('info')&quot;&gt;Info&lt;/button&gt;
    &lt;div id=&quot;info-toast&quot;&gt;&lt;/div&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script&gt;
    const coloredToast = (color) =&gt; {
        const toast = Swal.mixin({
            toast: true,
            position: 'bottom-start',
            showConfirmButton: false,
            timer: 3000,
            showCloseButton: true,
            customClass: {
                popup: `color-${color}`
            },
            target: document.getElementById(color + '-toast')
        });
        toast.fire({
            title: 'Example notification text.',
        });
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
    import highlight from '@/components/plugins/highlight.vue';
    import codePreview from '@/composables/codePreview';
    import Swal from 'sweetalert2';
    import { useAppStore } from '@/stores/index';
    import { useMeta } from '@/composables/use-meta';

    import IconBell from '@/components/icon/icon-bell.vue';
    import IconCode from '@/components/icon/icon-code.vue';

    useMeta({ title: 'Notification' });
    const store = useAppStore();

    const { codeArr, toggleCode } = codePreview();
    const showMessage = (msg = 'Example notification text.', position = 'bottom-start', showCloseButton = true, closeButtonHtml = '', duration = 3000) => {
        const toast = Swal.mixin({
            toast: true,
            position: <any>(position || 'bottom-start'),
            showConfirmButton: false,
            timer: duration,
            showCloseButton: showCloseButton,
        });
        toast.fire({
            title: msg,
        });
    };

    const clickCallable = () => {
        Swal.fire({
            toast: true,
            position: 'bottom-start',
            text: 'Custom callback when action button is clicked.',
            showCloseButton: true,
            showConfirmButton: false,
        }).then((result) => {
            Swal.fire({
                toast: true,
                position: 'bottom-start',
                text: 'Thanks for clicking the Dismiss button!',
                showCloseButton: true,
                showConfirmButton: false,
            });
        });
    };

    const coloredToast = (color) => {
        const toast = Swal.mixin({
            toast: true,
            position: 'bottom-start',
            showConfirmButton: false,
            timer: 3000,
            showCloseButton: true,
            customClass: {
                popup: `color-${color}`,
            },
            target: document.getElementById(color + '-toast') || 'body',
        });
        toast.fire({
            title: 'Example notification text.',
        });
    };
</script>
