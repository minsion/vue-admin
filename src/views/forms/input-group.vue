<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Forms</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Input Group</span>
            </li>
        </ul>
        <div class="pt-5 space-y-4">
            <!-- Basic -->
            <div class="grid grid-cols-1 xl:grid-cols-2 gap-4">
                <!-- default -->
                <div class="panel lg:row-span-2">
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
                        <form>
                            <div class="mb-5">
                                <div class="flex">
                                    <div
                                        class="bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                    >
                                        @
                                    </div>
                                    <input type="text" placeholder="Username" class="form-input ltr:rounded-l-none rtl:rounded-r-none" />
                                </div>
                            </div>
                            <div class="mb-5">
                                <div class="flex">
                                    <input type="text" placeholder="Recipient's username" class="form-input ltr:rounded-r-none rtl:rounded-l-none" />
                                    <div
                                        class="bg-[#eee] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                    >
                                        @example.com
                                    </div>
                                </div>
                            </div>
                            <div class="mb-5">
                                <label for="url">Your vanity URL</label>
                                <div class="flex">
                                    <div
                                        class="bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                    >
                                        https://
                                    </div>
                                    <input id="url" type="text" placeholder="example.com/users/" class="form-input ltr:rounded-l-none rtl:rounded-r-none" />
                                </div>
                            </div>
                            <div class="mb-5">
                                <div class="flex">
                                    <div
                                        class="bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                    >
                                        $
                                    </div>
                                    <input type="text" placeholder="" class="form-input rounded-none" />
                                    <div
                                        class="bg-[#eee] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                    >
                                        .00
                                    </div>
                                </div>
                            </div>
                            <div>
                                <div class="flex">
                                    <div
                                        class="bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b] whitespace-nowrap"
                                    >
                                        With textarea
                                    </div>
                                    <textarea rows="4" class="form-textarea ltr:rounded-l-none rtl:rounded-r-none"></textarea>
                                </div>
                            </div>
                        </form>
                    </div>
                    <template v-if="codeArr.includes('code1')">
                        <highlight>
                            <pre>
&lt;!-- basic --&gt;
&lt;form&gt;
  &lt;div class=&quot;mb-5&quot;&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;div
        class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
      &gt;
        @
      &lt;/div&gt;
      &lt;input type=&quot;text&quot; placeholder=&quot;Username&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none&quot; /&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div class=&quot;mb-5&quot;&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;input type=&quot;text&quot; placeholder=&quot;Recipient's username&quot; class=&quot;form-input ltr:rounded-r-none rtl:rounded-l-none&quot; /&gt;
      &lt;div
        class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
      &gt;
        @example.com
      &lt;/div&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div class=&quot;mb-5&quot;&gt;
    &lt;label for=&quot;url&quot;&gt;Your vanity URL&lt;/label&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;div
        class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
      &gt;
        https://
      &lt;/div&gt;
      &lt;input id=&quot;url&quot; type=&quot;text&quot; placeholder=&quot;example.com/users/&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none&quot; /&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div class=&quot;mb-5&quot;&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;div
        class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
      &gt;
        $
      &lt;/div&gt;
      &lt;input type=&quot;text&quot; placeholder=&quot;&quot; class=&quot;form-input rounded-none&quot; /&gt;
      &lt;div
        class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
      &gt;
        .00
      &lt;/div&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;div
        class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b] whitespace-nowrap&quot;
      &gt;
        With textarea
      &lt;/div&gt;
      &lt;textarea rows=&quot;4&quot; class=&quot;form-textarea ltr:rounded-l-none rtl:rounded-r-none&quot;&gt;&lt;/textarea&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/form&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- simple icon -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Simple Icon</h5>
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
                        <div class="mb-5">
                            <label for="iconLeft">Left</label>
                            <div class="flex">
                                <div
                                    class="bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                >
                                    <icon-bell-bing class="text-white-dark" />
                                </div>
                                <input id="iconLeft" type="text" placeholder="Notification" class="form-input ltr:rounded-l-none rtl:rounded-r-none" />
                            </div>
                        </div>
                        <div>
                            <label for="iconRight">Right</label>
                            <div class="flex">
                                <input id="iconRight" type="text" placeholder="Notification" class="form-input ltr:rounded-r-none rtl:rounded-l-none" />
                                <div
                                    class="bg-[#eee] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                >
                                    <icon-bell-bing class="text-white-dark" />
                                </div>
                            </div>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code2')">
                        <highlight>
                            <pre>
&lt;!-- left --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div
    class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
  &gt;
    &lt;svg&gt;...&lt;/svg&gt;
  &lt;/div&gt;
  &lt;input id=&quot;iconLeft&quot; type=&quot;text&quot; placeholder=&quot;Notification&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none&quot; /&gt;
&lt;/div&gt;

&lt;!-- right --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;input id=&quot;iconRight&quot; type=&quot;text&quot; placeholder=&quot;Notification&quot; class=&quot;form-input ltr:rounded-r-none rtl:rounded-l-none&quot; /&gt;
  &lt;div
    class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
  &gt;
    &lt;svg&gt;... &lt;/svg&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- spinning Icon -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Spinning Icon</h5>
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
                        <div class="mb-5">
                            <label for="spiLeft">Left</label>
                            <div class="flex">
                                <div
                                    class="bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                >
                                    <icon-loader class="text-white-dark animate-spin"/>
                                </div>
                                <input id="spiLeft" type="text" placeholder="Spinners" class="form-input ltr:rounded-l-none rtl:rounded-r-none" />
                            </div>
                        </div>
                        <div>
                            <label for="spiRight">Right</label>
                            <div class="flex">
                                <input id="spiRight" type="text" placeholder="Spinners" class="form-input ltr:rounded-r-none rtl:rounded-l-none" />
                                <div
                                    class="bg-[#eee] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                >
                                    <icon-loader class="text-white-dark animate-spin"/>
                                </div>
                            </div>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code3')">
                        <highlight>
                            <pre>
&lt;!-- left --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div
    class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
  &gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/div&gt;
  &lt;input id=&quot;spiLeft&quot; type=&quot;text&quot; placeholder=&quot;Spinners&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none&quot; /&gt;
&lt;/div&gt;

&lt;!-- right --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;input id=&quot;spiRight&quot; type=&quot;text&quot; placeholder=&quot;Spinners&quot; class=&quot;form-input ltr:rounded-r-none rtl:rounded-l-none&quot; /&gt;
  &lt;div
    class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
  &gt;
    &lt;svg&gt; ...  &lt;/svg&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- dropdown icon -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Dropdown Icon</h5>
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
                        <div class="dropdown mb-5">
                            <label for="dropdownLeft">Left</label>
                            <div class="flex">
                                <Popper
                                    :placement="store.rtlClass === 'rtl' ? 'bottom-end' : 'bottom-start'"
                                    offsetDistance="0"
                                    class="align-middle input-group-dropodwn"
                                >
                                    <div
                                        class="bg-primary flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] cursor-pointer h-full"
                                    >
                                        <icon-settings class="w-5 h-5 text-white" />
                                    </div>
                                    <template #content="{ close }">
                                        <ul @click="close()">
                                            <li><a href="javascript:;">Action</a></li>
                                            <li><a href="javascript:;">Another action</a></li>
                                            <li><a href="javascript:;">Something else here</a></li>
                                            <li><a href="javascript:;">Separated link</a></li>
                                        </ul>
                                    </template>
                                </Popper>
                                <input id="dropdownLeft" type="text" placeholder="Dropdown" class="form-input ltr:rounded-l-none rtl:rounded-r-none" />
                            </div>
                        </div>
                        <div class="dropdown">
                            <label for="dropdownRight">Right</label>
                            <div class="flex">
                                <input id="dropdownRight" type="text" placeholder="Dropdown" class="form-input ltr:rounded-r-none rtl:rounded-l-none" />
                                <Popper
                                    :placement="store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'"
                                    offsetDistance="0"
                                    class="align-middle input-group-dropodwn"
                                >
                                    <div
                                        class="bg-success flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] cursor-pointer h-full"
                                    >
                                        <icon-settings class="w-5 h-5 text-white" />
                                    </div>
                                    <template #content="{ close }">
                                        <ul @click="close()">
                                            <li><a href="javascript:;">Action</a></li>
                                            <li><a href="javascript:;">Another action</a></li>
                                            <li><a href="javascript:;">Something else here</a></li>
                                            <li><a href="javascript:;">Separated link</a></li>
                                        </ul>
                                    </template>
                                </Popper>
                            </div>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code4')">
                        <highlight>
                            <pre>
&lt;!-- left --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;Popper :placement=&quot;store.rtlClass === 'rtl' ? 'bottom-end' : 'bottom-start'&quot; offsetDistance=&quot;0&quot; class=&quot;align-middle input-group-dropodwn&quot;&gt;
    &lt;div
      class=&quot;bg-primary flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] cursor-pointer h-full&quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/div&gt;
    &lt;template #content=&quot;{ close }&quot;&gt;
      &lt;ul @click=&quot;close()&quot;&gt;
        &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Action&lt;/a&gt;&lt;/li&gt;
        &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Another action&lt;/a&gt;&lt;/li&gt;
        &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Something else here&lt;/a&gt;&lt;/li&gt;
        &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Separated link&lt;/a&gt;&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/template&gt;
  &lt;/Popper&gt;
  &lt;input id=&quot;dropdownLeft&quot; type=&quot;text&quot; placeholder=&quot;Dropdown&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none&quot; /&gt;
&lt;/div&gt;

&lt;!-- right --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;input id=&quot;dropdownRight&quot; type=&quot;text&quot; placeholder=&quot;Dropdown&quot; class=&quot;form-input ltr:rounded-r-none rtl:rounded-l-none&quot; /&gt;
  &lt;Popper :placement=&quot;store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'&quot; offsetDistance=&quot;0&quot; class=&quot;align-middle input-group-dropodwn&quot;&gt;
    &lt;div
      class=&quot;bg-success flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] cursor-pointer h-full&quot;
    &gt;
      &lt;svg&gt; ... &lt;/svg&gt;
    &lt;/div&gt;
    &lt;template #content=&quot;{ close }&quot;&gt;
      &lt;ul @click=&quot;close()&quot;&gt;
        &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Action&lt;/a&gt;&lt;/li&gt;
        &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Another action&lt;/a&gt;&lt;/li&gt;
        &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Something else here&lt;/a&gt;&lt;/li&gt;
        &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Separated link&lt;/a&gt;&lt;/li&gt;
      &lt;/ul&gt;
    &lt;/template&gt;
  &lt;/Popper&gt;
&lt;/div&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- checkbox -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Checkboxes</h5>
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
                        <div class="mb-5">
                            <label for="checkLeft">Left</label>
                            <div class="flex">
                                <div
                                    class="bg-[#f1f2f3] dark:bg-[#1b2e4b] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c]"
                                >
                                    <input type="checkbox" class="form-checkbox border-[#e0e6ed] dark:border-white-dark ltr:mr-0 rtl:ml-0" checked />
                                </div>
                                <input id="checkLeft" type="text" placeholder="Checkbox" class="form-input ltr:rounded-l-none rtl:rounded-r-none" />
                            </div>
                        </div>
                        <div>
                            <label for="checkRight">Right</label>
                            <div class="flex">
                                <input id="checkRight" type="text" placeholder="Checkbox" class="form-input ltr:rounded-r-none rtl:rounded-l-none" />
                                <div
                                    class="bg-[#f1f2f3] dark:bg-[#1b2e4b] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c]"
                                >
                                    <input
                                        type="checkbox"
                                        class="form-checkbox text-warning border-[#e0e6ed] dark:border-white-dark ltr:mr-0 rtl:ml-0"
                                        checked
                                    />
                                </div>
                            </div>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code5')">
                        <highlight>
                            <pre>
&lt;!-- left --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div
    class=&quot;bg-[#f1f2f3] dark:bg-[#1b2e4b] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c]&quot;
  &gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox border-[#e0e6ed] dark:border-white-dark ltr:mr-0 rtl:ml-0&quot; checked /&gt;
  &lt;/div&gt;
  &lt;input id=&quot;checkLeft&quot; type=&quot;text&quot; placeholder=&quot;Checkbox&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none&quot; /&gt;
&lt;/div&gt;

&lt;!-- right --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;input id=&quot;checkRight&quot; type=&quot;text&quot; placeholder=&quot;Checkbox&quot; class=&quot;form-input ltr:rounded-r-none rtl:rounded-l-none&quot; /&gt;
  &lt;div
    class=&quot;bg-[#f1f2f3] dark:bg-[#1b2e4b] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c]&quot;
  &gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox text-warning border-[#e0e6ed] dark:border-white-dark ltr:mr-0 rtl:ml-0&quot; checked /&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- radio -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Radios</h5>
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
                        <div class="mb-5">
                            <label for="radioLeft">Left</label>
                            <div class="flex">
                                <div
                                    class="bg-[#f1f2f3] dark:bg-[#1b2e4b] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c]"
                                >
                                    <input type="radio" class="form-radio text-info border-[#e0e6ed] dark:border-white-dark ltr:mr-0 rtl:ml-0" checked />
                                </div>
                                <input id="radioLeft" type="text" placeholder="Radio" class="form-input ltr:rounded-l-none rtl:rounded-r-none" />
                            </div>
                        </div>
                        <div>
                            <label for="radioRight">Right</label>
                            <div class="flex">
                                <input id="radioRight" type="text" placeholder="Radio" class="form-input ltr:rounded-r-none rtl:rounded-l-none" />
                                <div
                                    class="bg-[#f1f2f3] dark:bg-[#1b2e4b] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c]"
                                >
                                    <input type="radio" class="form-radio text-danger border-[#e0e6ed] dark:border-white-dark ltr:mr-0 rtl:ml-0" checked />
                                </div>
                            </div>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code6')">
                        <highlight>
                            <pre>
&lt;!-- left --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div
    class=&quot;bg-[#f1f2f3] dark:bg-[#1b2e4b] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c]&quot;
  &gt;
    &lt;input type=&quot;radio&quot; class=&quot;form-radio text-info border-[#e0e6ed] dark:border-white-dark ltr:mr-0 rtl:ml-0&quot; checked /&gt;
  &lt;/div&gt;
  &lt;input id=&quot;radioLeft&quot; type=&quot;text&quot; placeholder=&quot;Radio&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none&quot; /&gt;
&lt;/div&gt;

&lt;!-- right --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;input id=&quot;radioRight&quot; type=&quot;text&quot; placeholder=&quot;Radio&quot; class=&quot;form-input ltr:rounded-r-none rtl:rounded-l-none&quot; /&gt;
  &lt;div
    class=&quot;bg-[#f1f2f3] dark:bg-[#1b2e4b] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c]&quot;
  &gt;
    &lt;input type=&quot;radio&quot; class=&quot;form-radio text-danger border-[#e0e6ed] dark:border-white-dark ltr:mr-0 rtl:ml-0&quot; checked /&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- switch -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Switch</h5>
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
                        <div class="mb-5">
                            <label for="switchLeft">Left</label>
                            <div class="flex">
                                <div
                                    class="bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                >
                                    <label class="w-7 h-4 relative cursor-pointer mb-0">
                                        <input
                                            type="checkbox"
                                            class="peer absolute w-full h-full opacity-0 z-10 focus:ring-0 focus:outline-none cursor-pointer"
                                            id="custom_switch_checkbox1"
                                        />
                                        <span
                                            class="rounded-full border border-[#adb5bd] bg-white peer-checked:bg-primary peer-checked:border-primary dark:bg-dark block h-full before:absolute ltr:before:left-0.5 rtl:before:right-0.5 ltr:peer-checked:before:left-3.5 rtl:peer-checked:before:right-3.5 peer-checked:before:bg-white before:bg-[#adb5bd] dark:before:bg-white-dark before:bottom-[2px] before:w-3 before:h-3 before:rounded-full before:transition-all before:duration-300"
                                        ></span>
                                    </label>
                                </div>
                                <input id="switchLeft" type="text" placeholder="Switch" class="form-input ltr:rounded-l-none rtl:rounded-r-none" />
                            </div>
                        </div>
                        <div>
                            <label for="switchRight">Right</label>
                            <div class="flex">
                                <input id="switchRight" type="text" placeholder="Switch" class="form-input ltr:rounded-r-none rtl:rounded-l-none" />
                                <div
                                    class="bg-[#eee] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                >
                                    <label class="w-7 h-4 relative cursor-pointer mb-0">
                                        <input
                                            type="checkbox"
                                            class="peer absolute w-full h-full opacity-0 z-10 focus:ring-0 focus:outline-none cursor-pointer"
                                            id="custom_switch_checkbox2"
                                        />
                                        <span
                                            class="rounded-full border border-[#adb5bd] bg-white peer-checked:bg-primary peer-checked:border-primary dark:bg-dark block h-full before:absolute ltr:before:left-0.5 rtl:before:right-0.5 ltr:peer-checked:before:left-3.5 rtl:peer-checked:before:right-3.5 peer-checked:before:bg-white before:bg-[#adb5bd] dark:before:bg-white-dark before:bottom-[2px] before:w-3 before:h-3 before:rounded-full before:transition-all before:duration-300"
                                        ></span>
                                    </label>
                                </div>
                            </div>
                        </div>
                    </div>
                    <template v-if="codeArr.includes('code7')">
                        <highlight>
                            <pre>
&lt;!-- left --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div
    class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
  &gt;
    &lt;label class=&quot;w-7 h-4 relative cursor-pointer mb-0&quot;&gt;
      &lt;input type=&quot;checkbox&quot; class=&quot;peer absolute w-full h-full opacity-0 z-10 focus:ring-0 focus:outline-none cursor-pointer&quot; id=&quot;custom_switch_checkbox1&quot; /&gt;
      &lt;span
        class=&quot;rounded-full border border-[#adb5bd] bg-white peer-checked:bg-primary peer-checked:border-primary dark:bg-dark block h-full before:absolute ltr:before:left-0.5 rtl:before:right-0.5 ltr:peer-checked:before:left-3.5 rtl:peer-checked:before:right-3.5 peer-checked:before:bg-white before:bg-[#adb5bd] dark:before:bg-white-dark before:bottom-[2px] before:w-3 before:h-3 before:rounded-full before:transition-all before:duration-300&quot;
      &gt;&lt;/span&gt;
    &lt;/label&gt;
  &lt;/div&gt;
  &lt;input id=&quot;switchLeft&quot; type=&quot;text&quot; placeholder=&quot;Switch&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none&quot; /&gt;
&lt;/div&gt;

&lt;!-- right --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;input id=&quot;switchRight&quot; type=&quot;text&quot; placeholder=&quot;Switch&quot; class=&quot;form-input ltr:rounded-r-none rtl:rounded-l-none&quot; /&gt;
  &lt;div
    class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
  &gt;
    &lt;label class=&quot;w-7 h-4 relative cursor-pointer mb-0&quot;&gt;
      &lt;input type=&quot;checkbox&quot; class=&quot;peer absolute w-full h-full opacity-0 z-10 focus:ring-0 focus:outline-none cursor-pointer&quot; id=&quot;custom_switch_checkbox2&quot; /&gt;
      &lt;span
        class=&quot;rounded-full border border-[#adb5bd] bg-white peer-checked:bg-primary peer-checked:border-primary dark:bg-dark block h-full before:absolute ltr:before:left-0.5 rtl:before:right-0.5 ltr:peer-checked:before:left-3.5 rtl:peer-checked:before:right-3.5 peer-checked:before:bg-white before:bg-[#adb5bd] dark:before:bg-white-dark before:bottom-[2px] before:w-3 before:h-3 before:rounded-full before:transition-all before:duration-300&quot;
      &gt;&lt;/span&gt;
    &lt;/label&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
            </div>
            <!-- Sizes -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Sizes</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code8')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <form>
                        <div class="mb-5">
                            <div class="flex">
                                <div
                                    class="bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                >
                                    Small
                                </div>
                                <input type="text" placeholder="Username" class="form-input ltr:rounded-l-none rtl:rounded-r-none py-2.5 text-base" />
                            </div>
                        </div>
                        <div class="mb-5">
                            <div class="flex">
                                <div
                                    class="bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                >
                                    Small
                                </div>
                                <input type="text" placeholder="Username" class="form-input ltr:rounded-l-none rtl:rounded-r-none" />
                            </div>
                        </div>
                        <div>
                            <div class="flex">
                                <div
                                    class="bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                >
                                    Small
                                </div>
                                <input type="text" placeholder="Username" class="form-input ltr:rounded-l-none rtl:rounded-r-none py-1.5 text-xs" />
                            </div>
                        </div>
                    </form>
                </div>
                <template v-if="codeArr.includes('code8')">
                    <highlight>
                        <pre>
&lt;!-- sizes --&gt;
&lt;form&gt;
  &lt;div class=&quot;mb-5&quot;&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;div
        class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
      &gt;
        Small
      &lt;/div&gt;
      &lt;input type=&quot;text&quot; placeholder=&quot;Username&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none py-2.5 text-base&quot; /&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div class=&quot;mb-5&quot;&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;div
        class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
      &gt;
        Small
      &lt;/div&gt;
      &lt;input type=&quot;text&quot; placeholder=&quot;Username&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none&quot; /&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;div
        class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
      &gt;
        Small
      &lt;/div&gt;
      &lt;input type=&quot;text&quot; placeholder=&quot;Username&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none py-1.5 text-xs&quot; /&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/form&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Multiple -->
            <div class="grid grid-cols-1 xl:grid-cols-2 gap-4">
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Multiple inputs</h5>
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
                        <form>
                            <div class="flex">
                                <div
                                    class="bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                >
                                    First and last name
                                </div>
                                <input
                                    type="text"
                                    placeholder="First Name"
                                    class="form-input ltr:border-r-0 rtl:border-l-0 focus:!border-r focus:!border-l rounded-none flex-1"
                                />
                                <input type="text" placeholder="Last Name" class="form-input ltr:rounded-l-none rtl:rounded-r-none flex-1" />
                            </div>
                        </form>
                    </div>
                    <template v-if="codeArr.includes('code9')">
                        <highlight>
                            <pre>
&lt;!-- multiple inputs --&gt;
&lt;form&gt;
  &lt;div class=&quot;flex&quot;&gt;
    &lt;div
      class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
    &gt;
      First and last name
    &lt;/div&gt;
    &lt;input type=&quot;text&quot; placeholder=&quot;First Name&quot; class=&quot;form-input ltr:border-r-0 rtl:border-l-0 focus:!border-r focus:!border-l rounded-none flex-1&quot; /&gt;
    &lt;input type=&quot;text&quot; placeholder=&quot;Last Name&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none flex-1&quot; /&gt;
  &lt;/div&gt;
&lt;/form&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Multiple addons</h5>
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
                        <form>
                            <div class="mb-5">
                                <div class="flex">
                                    <div
                                        class="bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                    >
                                        $
                                    </div>
                                    <div
                                        class="bg-[#eee] flex justify-center items-center rounded-none px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                    >
                                        0.00
                                    </div>
                                    <input type="text" placeholder="" class="form-input ltr:rounded-l-none rtl:rounded-r-none flex-1" />
                                </div>
                            </div>
                            <div>
                                <div class="flex">
                                    <input
                                        type="text"
                                        placeholder=""
                                        class="form-input ltr:rounded-r-none rtl:rounded-l-none flex-1 ltr:rounded-l-md rtl:rounded-r-md"
                                    />
                                    <div
                                        class="bg-[#eee] flex justify-center items-center rounded-none px-3 font-semibold border border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                    >
                                        0.00
                                    </div>
                                    <div
                                        class="bg-[#eee] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]"
                                    >
                                        $
                                    </div>
                                </div>
                            </div>
                        </form>
                    </div>
                    <template v-if="codeArr.includes('code10')">
                        <highlight>
                            <pre>
&lt;!-- basic --&gt;
&lt;form&gt;
  &lt;div class=&quot;mb-5&quot;&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;div
        class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
      &gt;
        $
      &lt;/div&gt;
      &lt;div class=&quot;bg-[#eee] flex justify-center items-center rounded-none px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;&gt;
        0.00
      &lt;/div&gt;
      &lt;input type=&quot;text&quot; placeholder=&quot;&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none flex-1&quot; /&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;input type=&quot;text&quot; placeholder=&quot;&quot; class=&quot;form-input ltr:rounded-r-none rtl:rounded-l-none flex-1 ltr:rounded-l-md rtl:rounded-r-md&quot; /&gt;
      &lt;div class=&quot;bg-[#eee] flex justify-center items-center rounded-none px-3 font-semibold border border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;&gt;0.00&lt;/div&gt;
      &lt;div
        class=&quot;bg-[#eee] flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] dark:bg-[#1b2e4b]&quot;
      &gt;
        $
      &lt;/div&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/form&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
            </div>
            <div class="grid grid-cols-1 xl:grid-cols-2 gap-4">
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Buttons with dropdowns</h5>
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
                        <form>
                            <div class="mb-5 dropdown">
                                <label for="dropdownLeftButton">Left</label>
                                <div class="flex">
                                    <Popper
                                        :placement="store.rtlClass === 'rtl' ? 'bottom-end' : 'bottom-start'"
                                        offsetDistance="0"
                                        class="align-middle input-group-dropodwn"
                                    >
                                        <div
                                            class="bg-primary text-white flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] cursor-pointer h-full"
                                        >
                                            Dropdown
                                        </div>
                                        <template #content="{ close }">
                                            <ul @click="close()">
                                                <li><a href="javascript:;">Action</a></li>
                                                <li><a href="javascript:;">Another action</a></li>
                                                <li><a href="javascript:;">Something else here</a></li>
                                                <li><a href="javascript:;">Separated link</a></li>
                                            </ul>
                                        </template>
                                    </Popper>
                                    <input id="dropdownLeftButton" type="text" placeholder="" class="form-input ltr:rounded-l-none rtl:rounded-r-none" />
                                </div>
                            </div>
                            <div class="dropdown">
                                <label for="dropdownRightButton">Right</label>
                                <div class="flex">
                                    <input id="dropdownRightButton" type="text" placeholder="" class="form-input ltr:rounded-r-none rtl:rounded-l-none" />
                                    <Popper
                                        :placement="store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'"
                                        offsetDistance="0"
                                        class="align-middle input-group-dropodwn"
                                    >
                                        <div
                                            class="bg-danger text-white flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] cursor-pointer h-full"
                                        >
                                            Dropdown
                                        </div>
                                        <template #content="{ close }">
                                            <ul @click="close()">
                                                <li><a href="javascript:;">Action</a></li>
                                                <li><a href="javascript:;">Another action</a></li>
                                                <li><a href="javascript:;">Something else here</a></li>
                                                <li><a href="javascript:;">Separated link</a></li>
                                            </ul>
                                        </template>
                                    </Popper>
                                </div>
                            </div>
                        </form>
                    </div>
                    <template v-if="codeArr.includes('code11')">
                        <highlight>
                            <pre>
&lt;!-- buttons with dropdowns --&gt;
&lt;form&gt;
  &lt;div class=&quot;mb-5 dropdown&quot;&gt;
    &lt;label for=&quot;dropdownLeftButton&quot;&gt;Left&lt;/label&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;Popper :placement=&quot;store.rtlClass === 'rtl' ? 'bottom-end' : 'bottom-start'&quot; offsetDistance=&quot;0&quot; class=&quot;align-middle input-group-dropodwn&quot;&gt;
        &lt;div
          class=&quot;bg-primary text-white flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-[#e0e6ed] dark:border-[#17263c] cursor-pointer h-full&quot;
        &gt;
          Dropdown
        &lt;/div&gt;
        &lt;template #content=&quot;{ close }&quot;&gt;
          &lt;ul @click=&quot;close()&quot;&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Action&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Another action&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Something else here&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Separated link&lt;/a&gt;&lt;/li&gt;
          &lt;/ul&gt;
        &lt;/template&gt;
      &lt;/Popper&gt;
      &lt;input id=&quot;dropdownLeftButton&quot; type=&quot;text&quot; placeholder=&quot;&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none&quot; /&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div class=&quot;dropdown&quot;&gt;
    &lt;label for=&quot;dropdownRightButton&quot;&gt;Right&lt;/label&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;input id=&quot;dropdownRightButton&quot; type=&quot;text&quot; placeholder=&quot;&quot; class=&quot;form-input ltr:rounded-r-none rtl:rounded-l-none&quot; /&gt;
      &lt;Popper :placement=&quot;store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'&quot; offsetDistance=&quot;0&quot; class=&quot;align-middle input-group-dropodwn&quot;&gt;
        &lt;div
          class=&quot;bg-danger text-white flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-[#e0e6ed] dark:border-[#17263c] cursor-pointer h-full&quot;
        &gt;
          Dropdown
        &lt;/div&gt;
        &lt;template #content=&quot;{ close }&quot;&gt;
          &lt;ul @click=&quot;close()&quot;&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Action&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Another action&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Something else here&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Separated link&lt;/a&gt;&lt;/li&gt;
          &lt;/ul&gt;
        &lt;/template&gt;
      &lt;/Popper&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/form&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Segmented buttons</h5>
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
                        <form>
                            <div class="mb-5 dropdown">
                                <label for="btnLeft">Left</label>
                                <div class="flex">
                                    <div
                                        class="bg-info text-white flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-info"
                                    >
                                        Action
                                    </div>
                                    <Popper
                                        :placement="store.rtlClass === 'rtl' ? 'bottom-end' : 'bottom-start'"
                                        offsetDistance="0"
                                        class="align-middle input-group-dropodwn"
                                    >
                                        <div
                                            class="bg-white dark:bg-[#1b2e4b] text-info flex justify-center items-center rounded-none px-3 font-semibold border border-info cursor-pointer h-full"
                                        >
                                            <icon-caret-down class="w-5 h-5" />
                                        </div>
                                        <template #content="{ close }">
                                            <ul @click="close()">
                                                <li><a href="javascript:;">Action</a></li>
                                                <li><a href="javascript:;">Another action</a></li>
                                                <li><a href="javascript:;">Something else here</a></li>
                                                <li><a href="javascript:;">Separated link</a></li>
                                            </ul>
                                        </template>
                                    </Popper>
                                    <input
                                        id="btnLeft"
                                        type="text"
                                        placeholder=""
                                        class="form-input ltr:rounded-l-none rtl:rounded-r-none ltr:border-l-0 rtl:border-r-0"
                                    />
                                </div>
                            </div>
                            <div class="dropdown">
                                <label for="btnRight">Right</label>
                                <div class="flex">
                                    <input
                                        id="btnRight"
                                        type="text"
                                        placeholder=""
                                        class="form-input ltr:rounded-r-none rtl:rounded-l-none ltr:border-r-0 rtl:border-l-0"
                                    />
                                    <Popper
                                        :placement="store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'"
                                        offsetDistance="0"
                                        class="align-middle input-group-dropodwn"
                                    >
                                        <div
                                            class="bg-white dark:bg-[#1b2e4b] text-secondary flex justify-center items-center rounded-none px-3 font-semibold border border-secondary cursor-pointer h-full"
                                        >
                                            <icon-caret-down class="w-5 h-5" />
                                        </div>
                                        <template #content="{ close }">
                                            <ul @click="close()">
                                                <li><a href="javascript:;">Action</a></li>
                                                <li><a href="javascript:;">Another action</a></li>
                                                <li><a href="javascript:;">Something else here</a></li>
                                                <li><a href="javascript:;">Separated link</a></li>
                                            </ul>
                                        </template>
                                    </Popper>
                                    <div
                                        class="bg-secondary text-white flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-secondary cursor-pointer"
                                    >
                                        Action
                                    </div>
                                </div>
                            </div>
                        </form>
                    </div>
                    <template v-if="codeArr.includes('code12')">
                        <highlight>
                            <pre>
&lt;!-- segmented buttons --&gt;
&lt;form&gt;
  &lt;div class=&quot;mb-5 dropdown&quot;&gt;
    &lt;label for=&quot;btnLeft&quot;&gt;Left&lt;/label&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;div class=&quot;bg-info text-white flex justify-center items-center ltr:rounded-l-md rtl:rounded-r-md px-3 font-semibold border ltr:border-r-0 rtl:border-l-0 border-info&quot;&gt;Action&lt;/div&gt;
      &lt;Popper :placement=&quot;store.rtlClass === 'rtl' ? 'bottom-end' : 'bottom-start'&quot; offsetDistance=&quot;0&quot; class=&quot;align-middle input-group-dropodwn&quot;&gt;
        &lt;div class=&quot;bg-white dark:bg-[#1b2e4b] text-info flex justify-center items-center rounded-none px-3 font-semibold border border-info cursor-pointer h-full&quot;&gt;
          &lt;svg width=&quot;24&quot; height=&quot;24&quot; viewBox=&quot;0 0 24 24&quot; fill=&quot;none&quot; xmlns=&quot;http://www.w3.org/2000/svg&quot; class=&quot;w-5 h-5&quot;&gt;
            &lt;path d=&quot;M19 9L12 15L5 9&quot; stroke=&quot;currentColor&quot; stroke-width=&quot;1.5&quot; stroke-linecap=&quot;round&quot; stroke-linejoin=&quot;round&quot; /&gt;
          &lt;/svg&gt;
        &lt;/div&gt;
        &lt;template #content=&quot;{ close }&quot;&gt;
          &lt;ul @click=&quot;close()&quot;&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Action&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Another action&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Something else here&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Separated link&lt;/a&gt;&lt;/li&gt;
          &lt;/ul&gt;
        &lt;/template&gt;
      &lt;/Popper&gt;
      &lt;input id=&quot;btnLeft&quot; type=&quot;text&quot; placeholder=&quot;&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none ltr:border-l-0 rtl:border-r-0&quot; /&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div class=&quot;dropdown&quot;&gt;
    &lt;label for=&quot;btnRight&quot;&gt;Right&lt;/label&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;input id=&quot;btnRight&quot; type=&quot;text&quot; placeholder=&quot;&quot; class=&quot;form-input ltr:rounded-r-none rtl:rounded-l-none ltr:border-r-0 rtl:border-l-0&quot; /&gt;
      &lt;Popper :placement=&quot;store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'&quot; offsetDistance=&quot;0&quot; class=&quot;align-middle input-group-dropodwn&quot;&gt;
        &lt;div class=&quot;bg-white dark:bg-[#1b2e4b] text-secondary flex justify-center items-center rounded-none px-3 font-semibold border border-secondary cursor-pointer h-full&quot;&gt;
          &lt;svg width=&quot;24&quot; height=&quot;24&quot; viewBox=&quot;0 0 24 24&quot; fill=&quot;none&quot; xmlns=&quot;http://www.w3.org/2000/svg&quot; class=&quot;w-5 h-5&quot;&gt;
            &lt;path d=&quot;M19 9L12 15L5 9&quot; stroke=&quot;currentColor&quot; stroke-width=&quot;1.5&quot; stroke-linecap=&quot;round&quot; stroke-linejoin=&quot;round&quot; /&gt;
          &lt;/svg&gt;
        &lt;/div&gt;
        &lt;template #content=&quot;{ close }&quot;&gt;
          &lt;ul @click=&quot;close()&quot;&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Action&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Another action&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Something else here&lt;/a&gt;&lt;/li&gt;
            &lt;li&gt;&lt;a href=&quot;javascript:;&quot;&gt;Separated link&lt;/a&gt;&lt;/li&gt;
          &lt;/ul&gt;
        &lt;/template&gt;
      &lt;/Popper&gt;
      &lt;div
        class=&quot;bg-secondary text-white flex justify-center items-center ltr:rounded-r-md rtl:rounded-l-md px-3 font-semibold border ltr:border-l-0 rtl:border-r-0 border-secondary cursor-pointer&quot;
      &gt;
        Action
      &lt;/div&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/form&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
                <div class="panel lg:col-span-2">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Button addons</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code13')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <div class="mb-5">
                        <form>
                            <div class="mb-5">
                                <label for="addonsLeft">Left</label>
                                <div class="flex">
                                    <button type="button" class="btn btn-info ltr:rounded-r-none rtl:rounded-l-none">Button</button>
                                    <input id="addonsLeft" type="text" placeholder="" class="form-input ltr:rounded-l-none rtl:rounded-r-none" />
                                </div>
                            </div>
                            <div class="mb-5">
                                <label for="addonsRight">Right</label>
                                <div class="flex">
                                    <input id="addonsRight" type="text" placeholder="" class="form-input ltr:rounded-r-none rtl:rounded-l-none" />
                                    <button type="button" class="btn btn-secondary ltr:rounded-l-none rtl:rounded-r-none">Button</button>
                                </div>
                            </div>
                            <div class="mb-5">
                                <label for="addonsLeftoutline">Left</label>
                                <div class="flex">
                                    <button type="button" class="btn btn-outline-info ltr:rounded-r-none rtl:rounded-l-none">Button</button>
                                    <button type="button" class="btn btn-outline-info rounded-none ltr:border-l-0 rtl:border-r-0">Button</button>
                                    <input id="addonsLeftoutline" type="text" placeholder="" class="form-input ltr:rounded-l-none rtl:rounded-r-none" />
                                </div>
                            </div>
                            <div>
                                <label for="addonsRightoutline">Right</label>
                                <div class="flex">
                                    <input id="addonsRightoutline" type="text" placeholder="" class="form-input ltr:rounded-r-none rtl:rounded-l-none" />
                                    <button type="button" class="btn btn-outline-secondary rounded-none ltr:border-r-0 rtl:border-l-0">Button</button>
                                    <button type="button" class="btn btn-outline-secondary ltr:rounded-l-none rtl:rounded-r-none">Button</button>
                                </div>
                            </div>
                        </form>
                    </div>
                    <template v-if="codeArr.includes('code13')">
                        <highlight>
                            <pre>
&lt;!-- button addons --&gt;
&lt;form&gt;
  &lt;div class=&quot;mb-5&quot;&gt;
    &lt;label for=&quot;addonsLeft&quot;&gt;Left&lt;/label&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;button type=&quot;button&quot; class=&quot;btn btn-info ltr:rounded-r-none rtl:rounded-l-none&quot;&gt;Button&lt;/button&gt;
      &lt;input id=&quot;addonsLeft&quot; type=&quot;text&quot; placeholder=&quot;&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none&quot; /&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div class=&quot;mb-5&quot;&gt;
    &lt;label for=&quot;addonsRight&quot;&gt;Right&lt;/label&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;input id=&quot;addonsRight&quot; type=&quot;text&quot; placeholder=&quot;&quot; class=&quot;form-input ltr:rounded-r-none rtl:rounded-l-none&quot; /&gt;
      &lt;button type=&quot;button&quot; class=&quot;btn btn-secondary ltr:rounded-l-none rtl:rounded-r-none&quot;&gt;Button&lt;/button&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div class=&quot;mb-5&quot;&gt;
    &lt;label for=&quot;addonsLeftoutline&quot;&gt;Left&lt;/label&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;button type=&quot;button&quot; class=&quot;btn btn-outline-info ltr:rounded-r-none rtl:rounded-l-none&quot;&gt;Button&lt;/button&gt;
      &lt;button type=&quot;button&quot; class=&quot;btn btn-outline-info rounded-none ltr:border-l-0 rtl:border-r-0&quot;&gt;Button&lt;/button&gt;
      &lt;input id=&quot;addonsLeftoutline&quot; type=&quot;text&quot; placeholder=&quot;&quot; class=&quot;form-input ltr:rounded-l-none rtl:rounded-r-none&quot; /&gt;
    &lt;/div&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;label for=&quot;addonsRightoutline&quot;&gt;Right&lt;/label&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;input id=&quot;addonsRightoutline&quot; type=&quot;text&quot; placeholder=&quot;&quot; class=&quot;form-input ltr:rounded-r-none rtl:rounded-l-none&quot; /&gt;
      &lt;button type=&quot;button&quot; class=&quot;btn btn-outline-secondary rounded-none ltr:border-r-0 rtl:border-l-0&quot;&gt;Button&lt;/button&gt;
      &lt;button type=&quot;button&quot; class=&quot;btn btn-outline-secondary ltr:rounded-l-none rtl:rounded-r-none&quot;&gt;Button&lt;/button&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/form&gt;
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
    import { useAppStore } from '@/stores/index';
    import { useMeta } from '@/composables/use-meta';

    import IconCode from '@/components/icon/icon-code.vue';
    import IconBellBing from '@/components/icon/icon-bell-bing.vue';
    import IconLoader from '@/components/icon/icon-loader.vue';
    import IconSettings from '@/components/icon/icon-settings.vue';
    import IconCaretDown from '@/components/icon/icon-caret-down.vue';

    useMeta({ title: 'Input Group' });

    const store = useAppStore();
    const { codeArr, toggleCode } = codePreview();
</script>
