<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Components</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Media Object</span>
            </li>
        </ul>
        <div class="pt-5 grid grid-cols-1 xl:grid-cols-2 gap-6">
            <!-- Simple -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Simple</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code1')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-16 h-16 rounded" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg mb-2 text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code1')">
                    <highlight>
                        <pre>
&lt;!-- simple --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-16 h-16 rounded&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Order -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Order</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code2')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex">
                        <div class="flex-1 ltr:mr-4 rtl:ml-4">
                            <h4 class="font-semibold text-lg mb-2 text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                        <div>
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-16 h-16 rounded" />
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code2')">
                    <highlight>
                        <pre>
&lt;!-- order --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div class=&quot;flex-1 ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-16 h-16 rounded&quot; /&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Alignment -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Top-aligned media</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code3')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex items-start">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-16 h-16 rounded" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg mb-2 text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque. Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id
                                sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code3')">
                    <highlight>
                        <pre>
&lt;!-- top-aligned media --&gt;
&lt;div class=&quot;flex items-start&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-16 h-16 rounded&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque. Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu,
      gravida neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Center-aligned media</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code4')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex items-center">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-16 h-16 rounded" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg mb-2 text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque. Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id
                                sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code4')">
                    <highlight>
                        <pre>
&lt;!-- center aligned media --&gt;
&lt;div class=&quot;flex items-center&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-16 h-16 rounded&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque. Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu,
      gravida neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Bottom-aligned media</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code5')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex items-end">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-16 h-16 rounded" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg mb-2 text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque. Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id
                                sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code5')">
                    <highlight>
                        <pre>
&lt;!-- bottom aligned media --&gt;
&lt;div class=&quot;flex items-end&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-16 h-16 rounded&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque. Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu,
      gravida neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Right Aligned</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code6')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex">
                        <div class="flex-1 ltr:mr-4 rtl:ml-4 ltr:text-right rtl:text-left">
                            <h4 class="font-semibold text-lg mb-2 text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque. Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id
                                sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                        <div>
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-16 h-16 rounded" />
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code6')">
                    <highlight>
                        <pre>
&lt;!-- right aligned --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div class=&quot;flex-1 ltr:mr-4 rtl:ml-4 ltr:text-right rtl:text-left&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque. Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu,
      gravida neque.
    &lt;/p&gt;
  &lt;/div&gt;
  &lt;div&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-16 h-16 rounded&quot; /&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- List -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Media list</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code7')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex mb-5">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-14 h-14 rounded" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg mb-2 text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                    <div class="flex mb-5">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-14 h-14 rounded" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg mb-2 text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                    <div class="flex">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-14 h-14 rounded" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg mb-2 text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code7')">
                    <highlight>
                        <pre>
&lt;!-- list --&gt;
&lt;div class=&quot;flex mb-5&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-14 h-14 rounded&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
&lt;div class=&quot;flex mb-5&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-14 h-14 rounded&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-14 h-14 rounded&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Nesting -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Nesting</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code8')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-14 h-14 rounded" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg mb-2 text-primary">Heading</h4>
                            <p class="media-text mb-5">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                            <div class="flex">
                                <div class="ltr:mr-4 rtl:ml-4">
                                    <img src="/assets/images/profile-5.jpeg" alt="" class="w-14 h-14 rounded" />
                                </div>
                                <div class="flex-1">
                                    <h4 class="font-semibold text-lg mb-2 text-primary">Heading</h4>
                                    <p class="media-text">
                                        Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget
                                        dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code8')">
                    <highlight>
                        <pre>
&lt;!-- nesting --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-14 h-14 rounded&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text mb-5&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
    &lt;div class=&quot;flex&quot;&gt;
      &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
        &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-14 h-14 rounded&quot; /&gt;
      &lt;/div&gt;
      &lt;div class=&quot;flex-1&quot;&gt;
        &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading&lt;/h4&gt;
        &lt;p class=&quot;media-text&quot;&gt;
          Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu,
          gravida neque.
        &lt;/p&gt;
      &lt;/div&gt;
    &lt;/div&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Notation Text -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Notation Text</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code9')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-14 h-14 rounded" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg mb-2 text-primary">Heading</h4>
                            <p class="media-text mb-4">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                            <ul class="flex space-x-4 rtl:space-x-reverse font-bold">
                                <li><a href="javascript:;" class="hover:text-primary">Reply</a></li>
                                <li><a href="javascript:;" class="hover:text-primary">Edit</a></li>
                                <li><a href="javascript:;" class="hover:text-primary">Delete</a></li>
                            </ul>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code9')">
                    <highlight>
                        <pre>
&lt;!-- notation text --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-14 h-14 rounded&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text mb-4&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
    &lt;ul class=&quot;flex space-x-4 rtl:space-x-reverse font-bold&quot;&gt;
      &lt;li&gt;&lt;a href=&quot;javascript:;&quot; class=&quot;hover:text-primary&quot;&gt;Reply&lt;/a&gt;&lt;/li&gt;
      &lt;li&gt;&lt;a href=&quot;javascript:;&quot; class=&quot;hover:text-primary&quot;&gt;Edit&lt;/a&gt;&lt;/li&gt;
      &lt;li&gt;&lt;a href=&quot;javascript:;&quot; class=&quot;hover:text-primary&quot;&gt;Delete&lt;/a&gt;&lt;/li&gt;
    &lt;/ul&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Notation Icon -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Notation Icon</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code10')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-14 h-14 rounded" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg mb-2 text-primary">Heading</h4>
                            <p class="media-text mb-4">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                            <ul class="flex space-x-4 rtl:space-x-reverse font-bold">
                                <li>
                                    <a href="javascript:;" class="flex items-center hover:text-primary">
                                        <icon-message-dots class="w-4 h-4 ltr:mr-1 rtl:ml-1" />

                                        Reply
                                    </a>
                                </li>
                                <li>
                                    <a href="javascript:;" class="flex items-center hover:text-primary">
                                        <icon-pencil class="w-3.5 h-3.5 ltr:mr-1 rtl:ml-1" />

                                        Edit
                                    </a>
                                </li>
                                <li>
                                    <a href="javascript:;" class="flex items-center hover:text-primary">
                                        <icon-trash-lines class="w-4 h-4 ltr:mr-1 rtl:ml-1" />
                                        Delete
                                    </a>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code10')">
                    <highlight>
                        <pre>
&lt;!-- notation icon --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-14 h-14 rounded&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text mb-4&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
    &lt;ul class=&quot;flex space-x-4 rtl:space-x-reverse font-bold&quot;&gt;
      &lt;li&gt;
        &lt;a href=&quot;javascript:;&quot; class=&quot;flex items-center hover:text-primary&quot;&gt;
          &lt;svg&gt; ... &lt;/svg&gt;
          Reply
        &lt;/a&gt;
      &lt;/li&gt;
      &lt;li&gt;
        &lt;a href=&quot;javascript:;&quot; class=&quot;flex items-center hover:text-primary&quot;&gt;
          &lt;svg&gt; ... &lt;/svg&gt;
          Edit
        &lt;/a&gt;
      &lt;/li&gt;
      &lt;li&gt;
        &lt;a href=&quot;javascript:;&quot; class=&quot;flex items-center hover:text-primary&quot;&gt;
          &lt;svg&gt; ... &lt;/svg&gt;
          Delete
        &lt;/a&gt;
      &lt;/li&gt;
    &lt;/ul&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Badge -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Badge</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code11')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-14 h-14 rounded" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg mb-2 text-primary">
                                Heading <span class="badge bg-primary ltr:float-right rtl:float-left">Web Designer</span>
                            </h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code11')">
                    <highlight>
                        <pre>
&lt;!-- badge --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-14 h-14 rounded&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg mb-2 text-primary&quot;&gt;Heading &lt;span class=&quot;badge bg-primary ltr:float-right rtl:float-left&quot;&gt;Web Designer&lt;/span&gt;&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Dropdown -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Dropdown List</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code12')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <img src="/assets/images/profile-5.jpeg" alt="" class="w-14 h-14 rounded" />
                        </div>
                        <div class="flex-1">
                            <div class="flex justify-between mb-2">
                                <h4 class="font-semibold text-lg text-primary">Heading</h4>
                                <div class="dropdown">
                                    <Popper :placement="store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'" offsetDistance="0" class="align-middle">
                                        <a href="javascript:;">
                                            <icon-horizontal-dots class="opacity-70 text-white-dark" />
                                        </a>
                                        <template #content="{ close }">
                                            <ul @click="close()" class="whitespace-nowrap">
                                                <li>
                                                    <a href="javascript:;">
                                                        <icon-chat-dot class="ltr:mr-1 rtl:ml-1" />
                                                        Start chat
                                                    </a>
                                                </li>
                                                <li>
                                                    <a href="javascript:;">
                                                        <icon-phone class="ltr:mr-1 rtl:ml-1" />
                                                        Make a call
                                                    </a>
                                                </li>
                                                <li>
                                                    <a href="javascript:;">
                                                        <icon-bar-chart class="ltr:mr-1 rtl:ml-1" />

                                                        Statistics
                                                    </a>
                                                </li>
                                            </ul>
                                        </template>
                                    </Popper>
                                </div>
                            </div>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code12')">
                    <highlight>
                        <pre>
&lt;!-- dropdown --&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;img src=&quot;/assets/images/profile-5.jpeg&quot; alt=&quot;&quot; class=&quot;w-14 h-14 rounded&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;div class=&quot;flex justify-between mb-2&quot;&gt;
      &lt;h4 class=&quot;font-semibold text-lg text-primary&quot;&gt;Heading&lt;/h4&gt;
      &lt;div class=&quot;dropdown&quot;&gt;
        &lt;Popper :placement=&quot;store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'&quot; offsetDistance=&quot;0&quot; class=&quot;align-middle&quot;&gt;
          &lt;a href=&quot;javascript:;&quot;&gt;
            &lt;svg&gt; ... &lt;/svg&gt;
          &lt;/a&gt;
          &lt;template #content=&quot;{ close }&quot;&gt;
            &lt;ul @click=&quot;close()&quot; class=&quot;whitespace-nowrap&quot;&gt;
              &lt;li&gt;
                &lt;a href=&quot;javascript:;&quot;&gt;
                  &lt;svg&gt; ... &lt;/svg&gt;
                  Start chat
                &lt;/a&gt;
              &lt;/li&gt;
              &lt;li&gt;
                &lt;a href=&quot;javascript:;&quot;&gt;
                  &lt;svg&gt; ... &lt;/svg&gt;
                  Make a call
                &lt;/a&gt;
              &lt;/li&gt;
              &lt;li&gt;
                &lt;a href=&quot;javascript:;&quot;&gt;
                  &lt;svg&gt; ... &lt;/svg&gt;
                  Statistics
                &lt;/a&gt;
              &lt;/li&gt;
            &lt;/ul&gt;
          &lt;/template&gt;
        &lt;/Popper&gt;
      &lt;/div&gt;
    &lt;/div&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { useAppStore } from '@/stores/index';
const store = useAppStore();
&lt;/script&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Labels -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Labels</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code13')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex items-center mb-5">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <icon-x-circle class="w-7 h-7 text-danger" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                    <div class="flex items-center">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <icon-info-triangle class="w-7 h-7 text-warning" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code13')">
                    <highlight>
                        <pre>
&lt;!-- error --&gt;
&lt;div class=&quot;flex items-center mb-5&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
&lt;div class=&quot;flex items-center&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;svg&gt; ... &lt;/svg&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Checkbox -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Checkbox</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code14')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex mb-5">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <input type="checkbox" class="form-checkbox mt-1.5" checked />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                    <div class="flex">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <input type="checkbox" class="form-checkbox mt-1.5" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code14')">
                    <highlight>
                        <pre>
&lt;!-- checkbox --&gt;
&lt;div class=&quot;flex mb-5&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox mt-1.5&quot; checked /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox mt-1.5&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>
            <!-- Radio -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Radio</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code15')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="flex mb-5">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <input type="radio" class="form-radio mt-1.5" name="radio" checked />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                    <div class="flex">
                        <div class="ltr:mr-4 rtl:ml-4">
                            <input type="radio" class="form-radio mt-1.5" name="radio" />
                        </div>
                        <div class="flex-1">
                            <h4 class="font-semibold text-lg text-primary">Heading</h4>
                            <p class="media-text">
                                Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus.
                                Sed dapibus nulla elementum, rutrum neque eu, gravida neque.
                            </p>
                        </div>
                    </div>
                </div>
                <template v-if="codeArr.includes('code15')">
                    <highlight>
                        <pre>
&lt;!-- radio --&gt;
&lt;div class=&quot;flex mb-5&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;input type=&quot;radio&quot; class=&quot;form-radio mt-1.5&quot; name=&quot;radio&quot; checked /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
&lt;div class=&quot;flex&quot;&gt;
  &lt;div class=&quot;ltr:mr-4 rtl:ml-4&quot;&gt;
    &lt;input type=&quot;radio&quot; class=&quot;form-radio mt-1.5&quot; name=&quot;radio&quot; /&gt;
  &lt;/div&gt;
  &lt;div class=&quot;flex-1&quot;&gt;
    &lt;h4 class=&quot;font-semibold text-lg text-primary&quot;&gt;Heading&lt;/h4&gt;
    &lt;p class=&quot;media-text&quot;&gt;
      Fusce condimentum cursus mauris et ornare. Mauris fermentum mi id sollicitudin viverra. Aenean dignissim sed ante eget dapibus. Sed dapibus nulla elementum, rutrum neque eu, gravida
      neque.
    &lt;/p&gt;
  &lt;/div&gt;
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
    import { useAppStore } from '@/stores/index';
    import { useMeta } from '@/composables/use-meta';

    import IconCode from '@/components/icon/icon-code.vue';
    import IconMessageDots from '@/components/icon/icon-message-dots.vue';
    import IconPencil from '@/components/icon/icon-pencil.vue';
    import IconTrashLines from '@/components/icon/icon-trash-lines.vue';
    import IconHorizontalDots from '@/components/icon/icon-horizontal-dots.vue';
    import IconChatDot from '@/components/icon/icon-chat-dot.vue';
    import IconPhone from '@/components/icon/icon-phone.vue';
    import IconBarChart from '@/components/icon/icon-bar-chart.vue';
    import IconXCircle from '@/components/icon/icon-x-circle.vue';
    import IconInfoTriangle from '@/components/icon/icon-info-triangle.vue';


    useMeta({ title: 'Media Object' });
    const store = useAppStore();
    const { codeArr, toggleCode } = codePreview();
</script>
