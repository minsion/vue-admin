<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Forms</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Checkbox and Radio</span>
            </li>
        </ul>
        <div class="pt-5 space-y-8">
            <div class="space-y-8">
                <!-- Checkbox -->
                <h4 class="badge bg-primary inline-block hover:top-0 text-base mb-0">Checkbox</h4>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                    <div class="panel">
                        <div class="flex items-center justify-between mb-5">
                            <h5 class="font-semibold text-lg dark:text-white-light">Default</h5>
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
                            <div class="space-y-2">
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox" checked />
                                        <span>Primary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox text-success" />
                                        <span>Success</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox text-secondary" />
                                        <span>Secondary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox text-danger" />
                                        <span>Danger</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox text-warning" />
                                        <span>Warning</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox text-info" />
                                        <span>Info</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox text-dark" />
                                        <span>Dark</span>
                                    </label>
                                </div>
                            </div>
                        </div>
                        <template v-if="codeArr.includes('code1')">
                            <highlight>
                                <pre>
&lt;!-- default --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox&quot; checked /&gt;
    &lt;span&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-success&quot; /&gt;
    &lt;span&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-secondary&quot; /&gt;
    &lt;span&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-danger&quot; /&gt;
    &lt;span&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-warning&quot; /&gt;
    &lt;span&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-info&quot; /&gt;
    &lt;span&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-dark&quot; /&gt;
    &lt;span&gt;Dark&lt;/span&gt;
&lt;/label&gt;
</pre
                                >
                            </highlight>
                        </template>
                    </div>
                    <div class="panel">
                        <div class="flex items-center justify-between mb-5">
                            <h5 class="font-semibold text-lg dark:text-white-light">Default Rounded</h5>
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
                            <div class="space-y-2">
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox rounded-full" checked />
                                        <span>Primary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox text-success rounded-full" />
                                        <span>Success</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox text-secondary rounded-full" />
                                        <span>Secondary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox text-danger rounded-full" />
                                        <span>Danger</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox text-warning rounded-full" />
                                        <span>Warning</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox text-info rounded-full" />
                                        <span>Info</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox text-dark rounded-full" />
                                        <span>Dark</span>
                                    </label>
                                </div>
                            </div>
                        </div>
                        <template v-if="codeArr.includes('code2')">
                            <highlight>
                                <pre>
&lt;!-- rounded --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox rounded-full&quot; checked /&gt;
    &lt;span&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-success rounded-full&quot; /&gt;
    &lt;span&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-secondary rounded-full&quot; /&gt;
    &lt;span&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-danger rounded-full&quot; /&gt;
    &lt;span&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-warning rounded-full&quot; /&gt;
    &lt;span&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-info rounded-full&quot; /&gt;
    &lt;span&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-dark rounded-full&quot; /&gt;
    &lt;span&gt;Dark&lt;/span&gt;
&lt;/label&gt;
</pre
                                >
                            </highlight>
                        </template>
                    </div>
                    <div class="panel">
                        <div class="flex items-center justify-between mb-5">
                            <h5 class="font-semibold text-lg dark:text-white-light">Outline</h5>
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
                            <div class="space-y-2">
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-primary" checked />
                                        <span>Primary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-success" />
                                        <span>Success</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-secondary" />
                                        <span>Secondary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-danger" />
                                        <span>Danger</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-warning" />
                                        <span>Warning</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-info" />
                                        <span>Info</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-dark" />
                                        <span>Dark</span>
                                    </label>
                                </div>
                            </div>
                        </div>
                        <template v-if="codeArr.includes('code3')">
                            <highlight>
                                <pre>
&lt;!-- outline --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-primary&quot; checked /&gt;
    &lt;span&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-success&quot; /&gt;
    &lt;span&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-secondary&quot; /&gt;
    &lt;span&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-danger&quot; /&gt;
    &lt;span&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-warning&quot; /&gt;
    &lt;span&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-info&quot; /&gt;
    &lt;span&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-dark&quot; /&gt;
    &lt;span&gt;Dark&lt;/span&gt;
&lt;/label&gt;
</pre
                                >
                            </highlight>
                        </template>
                    </div>
                    <div class="panel">
                        <div class="flex items-center justify-between mb-5">
                            <h5 class="font-semibold text-lg dark:text-white-light">Outline Rounded</h5>
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
                            <div class="space-y-2">
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-primary rounded-full" checked />
                                        <span>Primary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-success rounded-full" />
                                        <span>Success</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-secondary rounded-full" />
                                        <span>Secondary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-danger rounded-full" />
                                        <span>Danger</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-warning rounded-full" />
                                        <span>Warning</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-info rounded-full" />
                                        <span>Info</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="checkbox" class="form-checkbox outline-dark rounded-full" />
                                        <span>Dark</span>
                                    </label>
                                </div>
                            </div>
                        </div>
                        <template v-if="codeArr.includes('code4')">
                            <highlight>
                                <pre>
&lt;!-- rounded --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-primary rounded-full&quot; checked /&gt;
    &lt;span&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-success rounded-full&quot; /&gt;
    &lt;span&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-secondary rounded-full&quot; /&gt;
    &lt;span&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-danger rounded-full&quot; /&gt;
    &lt;span&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-warning rounded-full&quot; /&gt;
    &lt;span&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-info rounded-full&quot; /&gt;
    &lt;span&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-dark rounded-full&quot; /&gt;
    &lt;span&gt;Dark&lt;/span&gt;
&lt;/label&gt;
</pre
                                >
                            </highlight>
                        </template>
                    </div>
                    <div class="panel">
                        <div class="flex items-center justify-between mb-5">
                            <h5 class="font-semibold text-lg dark:text-white-light">Default Text Color</h5>
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
                            <div class="grid grid-cols-2 gap-4">
                                <div class="space-y-2">
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox peer" checked />
                                            <span class="peer-checked:text-primary">Primary</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox text-success peer" />
                                            <span class="peer-checked:text-success">Success</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox text-secondary peer" />
                                            <span class="peer-checked:text-secondary">Secondary</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox text-danger peer" />
                                            <span class="peer-checked:text-danger">Danger</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox text-warning peer" />
                                            <span class="peer-checked:text-warning">Warning</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox text-info peer" />
                                            <span class="peer-checked:text-info">Info</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox text-dark peer" />
                                            <span class="peer-checked:text-dark">Dark</span>
                                        </label>
                                    </div>
                                </div>
                                <div class="space-y-2">
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-primary peer" checked />
                                            <span class="peer-checked:text-primary">Primary</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-success peer" />
                                            <span class="peer-checked:text-success">Success</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-secondary peer" />
                                            <span class="peer-checked:text-secondary">Secondary</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-danger peer" />
                                            <span class="peer-checked:text-danger">Danger</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-warning peer" />
                                            <span class="peer-checked:text-warning">Warning</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-info peer" />
                                            <span class="peer-checked:text-info">Info</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-dark peer" />
                                            <span class="peer-checked:text-dark">Dark</span>
                                        </label>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <template v-if="codeArr.includes('code5')">
                            <highlight>
                                <pre>
&lt;!-- default --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox peer&quot; checked /&gt;
    &lt;span class=&quot;peer-checked:text-primary&quot;&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-success peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-success&quot;&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-secondary peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-secondary&quot;&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-danger peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-danger&quot;&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-warning peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-warning&quot;&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-info peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-info&quot;&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-dark peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-dark&quot;&gt;Dark&lt;/span&gt;
&lt;/label&gt;

&lt;!-- outline --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-primary peer&quot; checked /&gt;
    &lt;span class=&quot;peer-checked:text-primary&quot;&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-success peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-success&quot;&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-secondary peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-secondary&quot;&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-danger peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-danger&quot;&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-warning peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-warning&quot;&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-info peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-info&quot;&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-dark peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-dark&quot;&gt;Dark&lt;/span&gt;
&lt;/label&gt;
</pre
                                >
                            </highlight>
                        </template>
                    </div>
                    <div class="panel">
                        <div class="flex items-center justify-between mb-5">
                            <h5 class="font-semibold text-lg dark:text-white-light">Rounded Text Color</h5>
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
                            <div class="grid grid-cols-2 gap-4">
                                <div class="space-y-2">
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox rounded-full peer" checked />
                                            <span class="peer-checked:text-primary">Primary</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox text-success rounded-full peer" />
                                            <span class="peer-checked:text-success">Success</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox text-secondary rounded-full peer" />
                                            <span class="peer-checked:text-secondary">Secondary</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox text-danger rounded-full peer" />
                                            <span class="peer-checked:text-danger">Danger</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox text-warning rounded-full peer" />
                                            <span class="peer-checked:text-warning">Warning</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox text-info rounded-full peer" />
                                            <span class="peer-checked:text-info">Info</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox text-dark rounded-full peer" />
                                            <span class="peer-checked:text-dark">Dark</span>
                                        </label>
                                    </div>
                                </div>
                                <div class="space-y-2">
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-primary rounded-full peer" checked />
                                            <span class="peer-checked:text-primary">Primary</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-success rounded-full peer" />
                                            <span class="peer-checked:text-success">Success</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-secondary rounded-full peer" />
                                            <span class="peer-checked:text-secondary">Secondary</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-danger rounded-full peer" />
                                            <span class="peer-checked:text-danger">Danger</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-warning rounded-full peer" />
                                            <span class="peer-checked:text-warning">Warning</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-info rounded-full peer" />
                                            <span class="peer-checked:text-info">Info</span>
                                        </label>
                                    </div>
                                    <div>
                                        <label class="inline-flex">
                                            <input type="checkbox" class="form-checkbox outline-dark rounded-full peer" />
                                            <span class="peer-checked:text-dark">Dark</span>
                                        </label>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <template v-if="codeArr.includes('code6')">
                            <highlight>
                                <pre>
&lt;!-- default --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox rounded-full peer&quot; checked /&gt;
    &lt;span class=&quot;peer-checked:text-primary&quot;&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-success rounded-full peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-success&quot;&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-secondary rounded-full peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-secondary&quot;&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-danger rounded-full peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-danger&quot;&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-warning rounded-full peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-warning&quot;&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-info rounded-full peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-info&quot;&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-dark rounded-full peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-dark&quot;&gt;Dark&lt;/span&gt;
&lt;/label&gt;

&lt;!-- outline --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-primary rounded-full peer&quot; checked /&gt;
    &lt;span class=&quot;peer-checked:text-primary&quot;&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-success rounded-full peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-success&quot;&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-secondary rounded-full peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-secondary&quot;&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-danger rounded-full peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-danger&quot;&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-warning rounded-full peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-warning&quot;&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-info rounded-full peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-info&quot;&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox outline-dark rounded-full peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-dark&quot;&gt;Dark&lt;/span&gt;
&lt;/label&gt;
</pre
                                >
                            </highlight>
                        </template>
                    </div>
                </div>
            </div>
            <div class="space-y-8">
                <!-- Radio -->
                <h4 class="badge bg-primary inline-block hover:top-0 text-base mb-0">Radio</h4>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                    <div class="panel">
                        <div class="flex items-center justify-between mb-5">
                            <h5 class="font-semibold text-lg dark:text-white-light">Default</h5>
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
                            <div class="space-y-2">
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_radio" class="form-radio" checked />
                                        <span>Primary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_radio" class="form-radio text-success" />
                                        <span>Success</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_radio" class="form-radio text-secondary" />
                                        <span>Secondary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_radio" class="form-radio text-danger" />
                                        <span>Danger</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_radio" class="form-radio text-warning" />
                                        <span>Warning</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_radio" class="form-radio text-info" />
                                        <span>Info</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_radio" class="form-radio text-dark" />
                                        <span>Dark</span>
                                    </label>
                                </div>
                            </div>
                        </div>
                        <template v-if="codeArr.includes('code7')">
                            <highlight>
                                <pre>
&lt;!-- radio --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_radio&quot; class=&quot;form-radio&quot; checked /&gt;
    &lt;span&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_radio&quot; class=&quot;form-radio text-success&quot; /&gt;
    &lt;span&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_radio&quot; class=&quot;form-radio text-secondary&quot; /&gt;
    &lt;span&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_radio&quot; class=&quot;form-radio text-danger&quot; /&gt;
    &lt;span&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_radio&quot; class=&quot;form-radio text-warning&quot; /&gt;
    &lt;span&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_radio&quot; class=&quot;form-radio text-info&quot; /&gt;
    &lt;span&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_radio&quot; class=&quot;form-radio text-dark&quot; /&gt;
    &lt;span&gt;Dark&lt;/span&gt;
&lt;/label&gt;
</pre
                                >
                            </highlight>
                        </template>
                    </div>
                    <div class="panel">
                        <div class="flex items-center justify-between mb-5">
                            <h5 class="font-semibold text-lg dark:text-white-light">Square</h5>
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
                            <div class="space-y-2">
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_radio" class="form-radio rounded-none" checked />
                                        <span>Primary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_radio" class="form-radio text-success rounded-none" />
                                        <span>Success</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_radio" class="form-radio text-secondary rounded-none" />
                                        <span>Secondary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_radio" class="form-radio text-danger rounded-none" />
                                        <span>Danger</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_radio" class="form-radio text-warning rounded-none" />
                                        <span>Warning</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_radio" class="form-radio text-info rounded-none" />
                                        <span>Info</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_radio" class="form-radio text-dark rounded-none" />
                                        <span>Dark</span>
                                    </label>
                                </div>
                            </div>
                        </div>
                        <template v-if="codeArr.includes('code8')">
                            <highlight>
                                <pre>
&lt;!-- square --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_radio&quot; class=&quot;form-radio rounded-none&quot; checked /&gt;
    &lt;span&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_radio&quot; class=&quot;form-radio text-success rounded-none&quot; /&gt;
    &lt;span&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_radio&quot; class=&quot;form-radio text-secondary rounded-none&quot; /&gt;
    &lt;span&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_radio&quot; class=&quot;form-radio text-danger rounded-none&quot; /&gt;
    &lt;span&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_radio&quot; class=&quot;form-radio text-warning rounded-none&quot; /&gt;
    &lt;span&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_radio&quot; class=&quot;form-radio text-info rounded-none&quot; /&gt;
    &lt;span&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_radio&quot; class=&quot;form-radio text-dark rounded-none&quot; /&gt;
    &lt;span&gt;Dark&lt;/span&gt;
&lt;/label&gt;
</pre
                                >
                            </highlight>
                        </template>
                    </div>
                    <div class="panel">
                        <div class="flex items-center justify-between mb-5">
                            <h5 class="font-semibold text-lg dark:text-white-light">Outline</h5>
                            <a
                                class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                                href="javascript:;"
                                @click="toggleCode('code9')"
                            >
                                <span class="flex items-center">
                                    <icon-code class="me-2" />
                                    Code
                                </span>
                            </a>
                        </div>
                        <div class="mb-5">
                            <div class="space-y-2">
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="outline_radio" class="form-radio outline-primary" checked />
                                        <span>Primary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="outline_radio" class="form-radio outline-success" />
                                        <span>Success</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="outline_radio" class="form-radio outline-secondary" />
                                        <span>Secondary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="outline_radio" class="form-radio outline-danger" />
                                        <span>Danger</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="outline_radio" class="form-radio outline-warning" />
                                        <span>Warning</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="outline_radio" class="form-radio outline-info" />
                                        <span>Info</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="outline_radio" class="form-radio outline-dark" />
                                        <span>Dark</span>
                                    </label>
                                </div>
                            </div>
                        </div>
                        <template v-if="codeArr.includes('code9')">
                            <highlight>
                                <pre>
&lt;!-- classic --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;outline_radio&quot; class=&quot;form-radio  outline-primary&quot; checked /&gt;
    &lt;span&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;outline_radio&quot; class=&quot;form-radio  outline-success&quot; /&gt;
    &lt;span&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;outline_radio&quot; class=&quot;form-radio  outline-secondary&quot; /&gt;
    &lt;span&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;outline_radio&quot; class=&quot;form-radio  outline-danger&quot; /&gt;
    &lt;span&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;outline_radio&quot; class=&quot;form-radio  outline-warning&quot; /&gt;
    &lt;span&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;outline_radio&quot; class=&quot;form-radio  outline-info&quot; /&gt;
    &lt;span&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;outline_radio&quot; class=&quot;form-radio  outline-dark&quot; /&gt;
    &lt;span&gt;Dark&lt;/span&gt;
&lt;/label&gt;
</pre
                                >
                            </highlight>
                        </template>
                    </div>
                    <div class="panel">
                        <div class="flex items-center justify-between mb-5">
                            <h5 class="font-semibold text-lg dark:text-white-light">Default Text Color</h5>
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
                        <div class="mb-5">
                            <div class="space-y-2">
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_text_color" class="form-radio peer" checked />
                                        <span class="peer-checked:text-primary">Primary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_text_color" class="form-radio text-success peer" />
                                        <span class="peer-checked:text-success">Success</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_text_color" class="form-radio text-secondary peer" />
                                        <span class="peer-checked:text-secondary">Secondary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_text_color" class="form-radio text-danger peer" />
                                        <span class="peer-checked:text-danger">Danger</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_text_color" class="form-radio text-warning peer" />
                                        <span class="peer-checked:text-warning">Warning</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_text_color" class="form-radio text-info peer" />
                                        <span class="peer-checked:text-info">Info</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="default_text_color" class="form-radio text-dark peer" />
                                        <span class="peer-checked:text-dark">Dark</span>
                                    </label>
                                </div>
                            </div>
                        </div>
                        <template v-if="codeArr.includes('code10')">
                            <highlight>
                                <pre>
&lt;!-- default text color --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_text_color&quot; class=&quot;form-radio peer&quot; checked /&gt;
    &lt;span class=&quot;peer-checked:text-primary&quot;&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_text_color&quot; class=&quot;form-radio text-success peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-success&quot;&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_text_color&quot; class=&quot;form-radio text-secondary peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-secondary&quot;&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_text_color&quot; class=&quot;form-radio text-danger peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-danger&quot;&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_text_color&quot; class=&quot;form-radio text-warning peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-warning&quot;&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_text_color&quot; class=&quot;form-radio text-info peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-info&quot;&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;default_text_color&quot; class=&quot;form-radio text-dark peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-dark&quot;&gt;Dark&lt;/span&gt;
&lt;/label&gt;
</pre
                                >
                            </highlight>
                        </template>
                    </div>
                    <div class="panel">
                        <div class="flex items-center justify-between mb-5">
                            <h5 class="font-semibold text-lg dark:text-white-light">Square Text Color</h5>
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
                        <div class="mb-5">
                            <div class="space-y-2">
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_text_radio" class="form-radio rounded-none peer" checked />
                                        <span class="peer-checked:text-primary">Primary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_text_radio" class="form-radio text-success rounded-none peer" />
                                        <span class="peer-checked:text-success">Success</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_text_radio" class="form-radio text-secondary rounded-none peer" />
                                        <span class="peer-checked:text-secondary">Secondary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_text_radio" class="form-radio text-danger rounded-none peer" />
                                        <span class="peer-checked:text-danger">Danger</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_text_radio" class="form-radio text-warning rounded-none peer" />
                                        <span class="peer-checked:text-warning">Warning</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_text_radio" class="form-radio text-info rounded-none peer" />
                                        <span class="peer-checked:text-info">Info</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="square_text_radio" class="form-radio text-dark rounded-none peer" />
                                        <span class="peer-checked:text-dark">Dark</span>
                                    </label>
                                </div>
                            </div>
                        </div>
                        <template v-if="codeArr.includes('code11')">
                            <highlight>
                                <pre>
&lt;!-- square text color --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_text_radio&quot; class=&quot;form-radio rounded-none peer&quot; checked /&gt;
    &lt;span class=&quot;peer-checked:text-primary&quot;&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_text_radio&quot; class=&quot;form-radio text-success rounded-none peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-success&quot;&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_text_radio&quot; class=&quot;form-radio text-secondary rounded-none peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-secondary&quot;&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_text_radio&quot; class=&quot;form-radio text-danger rounded-none peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-danger&quot;&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_text_radio&quot; class=&quot;form-radio text-warning rounded-none peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-warning&quot;&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_text_radio&quot; class=&quot;form-radio text-info rounded-none peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-info&quot;&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;square_text_radio&quot; class=&quot;form-radio text-dark rounded-none peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-dark&quot;&gt;Dark&lt;/span&gt;
&lt;/label&gt;
</pre
                                >
                            </highlight>
                        </template>
                    </div>
                    <div class="panel">
                        <div class="flex items-center justify-between mb-5">
                            <h5 class="font-semibold text-lg dark:text-white-light">Outline Text Color</h5>
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
                        <div class="mb-5">
                            <div class="space-y-2">
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="classic_text_radio" class="form-radio outline-primary peer" checked />
                                        <span class="peer-checked:text-primary">Primary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="classic_text_radio" class="form-radio outline-success peer" />
                                        <span class="peer-checked:text-success">Success</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="classic_text_radio" class="form-radio outline-secondary peer" />
                                        <span class="peer-checked:text-secondary">Secondary</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="classic_text_radio" class="form-radio outline-danger peer" />
                                        <span class="peer-checked:text-danger">Danger</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="classic_text_radio" class="form-radio outline-warning peer" />
                                        <span class="peer-checked:text-warning">Warning</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="classic_text_radio" class="form-radio outline-info peer" />
                                        <span class="peer-checked:text-info">Info</span>
                                    </label>
                                </div>
                                <div>
                                    <label class="inline-flex">
                                        <input type="radio" name="classic_text_radio" class="form-radio outline-dark peer" />
                                        <span class="peer-checked:text-dark">Dark</span>
                                    </label>
                                </div>
                            </div>
                        </div>
                        <template v-if="codeArr.includes('code12')">
                            <highlight>
                                <pre>
&lt;!-- classic text color --&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;classic_text_radio&quot; class=&quot;form-radio outline-primary peer&quot; checked /&gt;
    &lt;span class=&quot;peer-checked:text-primary&quot;&gt;Primary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;classic_text_radio&quot; class=&quot;form-radio outline-success peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-success&quot;&gt;Success&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;classic_text_radio&quot; class=&quot;form-radio outline-secondary peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-secondary&quot;&gt;Secondary&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;classic_text_radio&quot; class=&quot;form-radio outline-danger peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-danger&quot;&gt;Danger&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;classic_text_radio&quot; class=&quot;form-radio outline-warning peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-warning&quot;&gt;Warning&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;classic_text_radio&quot; class=&quot;form-radio outline-info peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-info&quot;&gt;Info&lt;/span&gt;
&lt;/label&gt;
&lt;label class=&quot;inline-flex&quot;&gt;
    &lt;input type=&quot;radio&quot; name=&quot;classic_text_radio&quot; class=&quot;form-radio outline-dark peer&quot; /&gt;
    &lt;span class=&quot;peer-checked:text-dark&quot;&gt;Dark&lt;/span&gt;
&lt;/label&gt;
</pre
                                >
                            </highlight>
                        </template>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts" setup>
    import highlight from '@/components/plugins/highlight.vue';
    import codePreview from '@/composables/codePreview';
    import { useMeta } from '@/composables/use-meta';

    import IconCode from '@/components/icon/icon-code.vue';

    useMeta({ title: 'Checkbox & Radio' });

    const { codeArr, toggleCode } = codePreview();
</script>
