<template>
    <div>
        <div class="grid grid-cols-1 xl:grid-cols-2 gap-6">
            <!-- Basic -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Simple Table</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code1')">
                        <span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span>
                    </a>
                </div>
                <div class="mb-5">
                    <div class="table-responsive">
                        <table>
                            <thead>
                                <tr>
                                    <th>Name</th>
                                    <th>Date</th>
                                    <th>Sale</th>
                                    <th class="text-center">Status</th>
                                    <th class="text-center">Action</th>
                                </tr>
                            </thead>
                            <tbody>
                                <template v-for="data in tableData" :key="data.id">
                                    <tr>
                                        <td class="whitespace-nowrap">{{ data.name }}</td>
                                        <td>{{ data.date }}</td>
                                        <td>{{ data.sale }}</td>
                                        <td
                                            class="text-center whitespace-nowrap"
                                            :class="{
                                                'text-success': data.status === 'Complete',
                                                'text-secondary': data.status === 'Pending',
                                                'text-info': data.status === 'In Progress',
                                                'text-danger': data.status === 'Canceled',
                                            }"
                                        >
                                            {{ data.status }}
                                        </td>
                                        <td class="text-center">
                                            <button type="button" v-tippy:delete>
                                                <icon-trash-lines class="m-auto" />
                                            </button>
                                            <tippy target="delete">Delete</tippy>
                                        </td>
                                    </tr>
                                </template>
                            </tbody>
                        </table>
                    </div>
                </div>
                <template v-if="codeArr.includes('code1')">
                    <highlight>
                        <pre>
&lt;!-- basic table --&gt;
&lt;div class=&quot;table-responsive&quot;&gt;
  &lt;table&gt;
    &lt;thead&gt;
      &lt;tr&gt;
        &lt;th&gt;Name&lt;/th&gt;
        &lt;th&gt;Date&lt;/th&gt;
        &lt;th&gt;Sale&lt;/th&gt;
        &lt;th class=&quot;text-center&quot;&gt;Status&lt;/th&gt;
        &lt;th class=&quot;text-center&quot;&gt;Action&lt;/th&gt;
      &lt;/tr&gt;
    &lt;/thead&gt;
    &lt;tbody&gt;
      &lt;template v-for=&quot;data in tableData&quot; :key=&quot;data.id&quot;&gt;
        &lt;tr&gt;
          &lt;td class=&quot;whitespace-nowrap&quot;&gt;&#123;&#123; data.name &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.date &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.sale &#125;&#125;&lt;/td&gt;
          &lt;td
            class=&quot;text-center whitespace-nowrap&quot;
            :class=&quot;{
              'text-success': data.status === 'Complete',
              'text-secondary': data.status === 'Pending',
              'text-info': data.status === 'In Progress',
              'text-danger': data.status === 'Canceled',
            }&quot;
          &gt;
            &#123;&#123; data.status &#125;&#125;
          &lt;/td&gt;
          &lt;td class=&quot;text-center&quot;&gt;
            &lt;button type=&quot;button&quot; v-tippy:delete&gt;
              &lt;svg&gt; ... &lt;/svg&gt;
            &lt;/button&gt;
            &lt;tippy target=&quot;delete&quot;&gt;Delete&lt;/tippy&gt;
          &lt;/td&gt;
        &lt;/tr&gt;
      &lt;/template&gt;
    &lt;/tbody&gt;
  &lt;/table&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref } from 'vue';
const tableData = ref([
  {
    id: 1,
    name: 'John Doe',
    email: 'johndoe@yahoo.com',
    date: '10/08/2020',
    sale: 120,
    status: 'Complete',
    register: '5 min ago',
    progress: '40%',
    position: 'Developer',
    office: 'London',
  },
  .....
]);
&lt;/script&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- Hover Table -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Hover Table</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code2')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        ></a
                    >
                </div>
                <div class="mb-5">
                    <div class="table-responsive">
                        <table class="table-hover">
                            <thead>
                                <tr>
                                    <th>Name</th>
                                    <th>Date</th>
                                    <th>Sale</th>
                                    <th class="text-center">Status</th>
                                    <th class="text-center">Action</th>
                                </tr>
                            </thead>
                            <tbody>
                                <template v-for="data in tableData" :key="data.id">
                                    <tr>
                                        <td class="whitespace-nowrap">{{ data.name }}</td>
                                        <td>{{ data.date }}</td>
                                        <td>{{ data.sale }}</td>
                                        <td
                                            class="text-center whitespace-nowrap"
                                            :class="{
                                                'text-success': data.status === 'Complete',
                                                'text-secondary': data.status === 'Pending',
                                                'text-info': data.status === 'In Progress',
                                                'text-danger': data.status === 'Canceled',
                                            }"
                                        >
                                            {{ data.status }}
                                        </td>
                                        <td class="text-center">
                                            <button type="button" v-tippy:delete>
                                                <icon-trash-lines class="m-auto" />
                                            </button>
                                            <tippy target="delete">Delete</tippy>
                                        </td>
                                    </tr>
                                </template>
                            </tbody>
                        </table>
                    </div>
                </div>
                <template v-if="codeArr.includes('code2')">
                    <highlight>
                        <pre>
&lt;!-- hover table --&gt;
&lt;div class=&quot;table-responsive&quot;&gt;
  &lt;table class=&quot;table-hover&quot;&gt;
    &lt;thead&gt;
      &lt;tr&gt;
        &lt;th&gt;Name&lt;/th&gt;
        &lt;th&gt;Date&lt;/th&gt;
        &lt;th&gt;Sale&lt;/th&gt;
        &lt;th class=&quot;text-center&quot;&gt;Status&lt;/th&gt;
        &lt;th class=&quot;text-center&quot;&gt;Action&lt;/th&gt;
      &lt;/tr&gt;
    &lt;/thead&gt;
    &lt;tbody&gt;
      &lt;template v-for=&quot;data in tableData&quot; :key=&quot;data.id&quot;&gt;
        &lt;tr&gt;
          &lt;td class=&quot;whitespace-nowrap&quot;&gt;&#123;&#123; data.name &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.date &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.sale &#125;&#125;&lt;/td&gt;
          &lt;td
            class=&quot;text-center whitespace-nowrap&quot;
            :class=&quot;{
              'text-success': data.status === 'Complete',
              'text-secondary': data.status === 'Pending',
              'text-info': data.status === 'In Progress',
              'text-danger': data.status === 'Canceled',
            }&quot;
          &gt;
            &#123;&#123; data.status &#125;&#125;
          &lt;/td&gt;
          &lt;td class=&quot;text-center&quot;&gt;
            &lt;button type=&quot;button&quot; v-tippy:delete&gt;
              &lt;svg&gt; ... &lt;/svg&gt;
            &lt;/button&gt;
            &lt;tippy target=&quot;delete&quot;&gt;Delete&lt;/tippy&gt;
          &lt;/td&gt;
        &lt;/tr&gt;
      &lt;/template&gt;
    &lt;/tbody&gt;
  &lt;/table&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref } from 'vue';
const tableData = ref([
  {
    id: 1,
    name: 'John Doe',
    email: 'johndoe@yahoo.com',
    date: '10/08/2020',
    sale: 120,
    status: 'Complete',
    register: '5 min ago',
    progress: '40%',
    position: 'Developer',
    office: 'London',
  },
  .....
]);
&lt;/script&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- stripped table -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Striped Table</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code3')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        ></a
                    >
                </div>
                <div class="mb-5">
                    <div class="table-responsive">
                        <table class="table-striped">
                            <thead>
                                <tr>
                                    <th>Name</th>
                                    <th>Date</th>
                                    <th>Sale</th>
                                    <th></th>
                                </tr>
                            </thead>
                            <tbody>
                                <template v-for="data in tableData" :key="data.id">
                                    <tr>
                                        <td class="whitespace-nowrap">{{ data.name }}</td>
                                        <td>{{ data.date }}</td>
                                        <td>{{ data.sale }}</td>
                                        <td class="text-center">
                                            <button type="button" v-tippy:delete>
                                                <icon-trash-lines class="m-auto" />
                                            </button>
                                            <tippy target="delete">Delete</tippy>
                                        </td>
                                    </tr>
                                </template>
                            </tbody>
                        </table>
                    </div>
                </div>
                <template v-if="codeArr.includes('code3')">
                    <highlight>
                        <pre>
&lt;!-- striped table --&gt;
&lt;div class=&quot;table-responsive&quot;&gt;
  &lt;table class=&quot;table-striped&quot;&gt;
    &lt;thead&gt;
      &lt;tr&gt;
        &lt;th&gt;Name&lt;/th&gt;
        &lt;th&gt;Date&lt;/th&gt;
        &lt;th&gt;Sale&lt;/th&gt;
        &lt;th&gt;&lt;/th&gt;
      &lt;/tr&gt;
    &lt;/thead&gt;
    &lt;tbody&gt;
      &lt;template v-for=&quot;data in tableData&quot; :key=&quot;data.id&quot;&gt;
        &lt;tr&gt;
          &lt;td class=&quot;whitespace-nowrap&quot;&gt;&#123;&#123; data.name &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.date &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.sale &#125;&#125;&lt;/td&gt;
          &lt;td class=&quot;text-center&quot;&gt;
            &lt;button type=&quot;button&quot; v-tippy:delete&gt;
              &lt;svg&gt; ... &lt;/svg&gt;
            &lt;/button&gt;
            &lt;tippy target=&quot;delete&quot;&gt;Delete&lt;/tippy&gt;
          &lt;/td&gt;
        &lt;/tr&gt;
      &lt;/template&gt;
    &lt;/tbody&gt;
  &lt;/table&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref } from 'vue';
const tableData = ref([
  {
    id: 1,
    name: 'John Doe',
    email: 'johndoe@yahoo.com',
    date: '10/08/2020',
    sale: 120,
    status: 'Complete',
    register: '5 min ago',
    progress: '40%',
    position: 'Developer',
    office: 'London',
  },
  .....
]);
&lt;/script&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- Table Light -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Table Light</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code4')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        ></a
                    >
                </div>
                <div class="mb-5">
                    <div class="table-responsive">
                        <table class="table-hover">
                            <thead>
                                <tr class="!bg-transparent dark:!bg-transparent">
                                    <th>#</th>
                                    <th>Name</th>
                                    <th>Email</th>
                                    <th>Created At</th>
                                    <th class="text-center"></th>
                                </tr>
                            </thead>
                            <tbody>
                                <template v-for="data in tableData" :key="data.id">
                                    <tr>
                                        <td>{{ data.id }}</td>
                                        <td class="whitespace-nowrap">{{ data.name }}</td>
                                        <td>{{ data.email }}</td>
                                        <td>{{ data.date }}</td>
                                        <td class="text-center">
                                            <button type="button" v-tippy:delete>
                                                <icon-x-circle class="m-auto" />
                                            </button>
                                            <tippy target="delete">Delete</tippy>
                                        </td>
                                    </tr>
                                </template>
                            </tbody>
                        </table>
                    </div>
                </div>
                <template v-if="codeArr.includes('code4')">
                    <highlight>
                        <pre>
&lt;!-- table light --&gt;
&lt;div class=&quot;table-responsive&quot;&gt;
  &lt;table class=&quot;table-hover&quot;&gt;
    &lt;thead&gt;
      &lt;tr class=&quot;!bg-transparent dark:!bg-transparent&quot;&gt;
        &lt;th&gt;#&lt;/th&gt;
        &lt;th&gt;Name&lt;/th&gt;
        &lt;th&gt;Email&lt;/th&gt;
        &lt;th&gt;Created At&lt;/th&gt;
        &lt;th class=&quot;text-center&quot;&gt;&lt;/th&gt;
      &lt;/tr&gt;
    &lt;/thead&gt;
    &lt;tbody&gt;
      &lt;template v-for=&quot;data in tableData&quot; :key=&quot;data.id&quot;&gt;
        &lt;tr&gt;
          &lt;td&gt;&#123;&#123; data.id &#125;&#125;&lt;/td&gt;
          &lt;td class=&quot;whitespace-nowrap&quot;&gt;&#123;&#123; data.name &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.email &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.date &#125;&#125;&lt;/td&gt;
          &lt;td class=&quot;text-center&quot;&gt;
            &lt;button type=&quot;button&quot; v-tippy:delete&gt;
              &lt;svg&gt; ... &lt;/svg&gt;
            &lt;/button&gt;
            &lt;tippy target=&quot;delete&quot;&gt;Delete&lt;/tippy&gt;
          &lt;/td&gt;
        &lt;/tr&gt;
      &lt;/template&gt;
    &lt;/tbody&gt;
  &lt;/table&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref } from 'vue';
const tableData = ref([
  {
    id: 1,
    name: 'John Doe',
    email: 'johndoe@yahoo.com',
    date: '10/08/2020',
    sale: 120,
    status: 'Complete',
    register: '5 min ago',
    progress: '40%',
    position: 'Developer',
    office: 'London',
  },
  .....
]);
&lt;/script&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- captions -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Captions</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code5')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        ></a
                    >
                </div>
                <div class="mb-5">
                    <div class="table-responsive">
                        <table>
                            <thead>
                                <tr>
                                    <th>#</th>
                                    <th>Name</th>
                                    <th>Email</th>
                                    <th>Status</th>
                                    <th class="text-center">Register</th>
                                </tr>
                            </thead>
                            <tbody>
                                <template v-for="data in tableData" :key="data.id">
                                    <tr>
                                        <td>{{ data.id }}</td>
                                        <td class="whitespace-nowrap">{{ data.name }}</td>
                                        <td>{{ data.email }}</td>
                                        <td>
                                            <span
                                                class="badge whitespace-nowrap"
                                                :class="{
                                                    'badge-outline-primary': data.status === 'Complete',
                                                    'badge-outline-secondary': data.status === 'Pending',
                                                    'badge-outline-info': data.status === 'In Progress',
                                                    'badge-outline-danger': data.status === 'Canceled',
                                                }"
                                                >{{ data.status }}</span
                                            >
                                        </td>
                                        <td class="text-center">{{ data.register }}</td>
                                    </tr>
                                </template>
                            </tbody>
                        </table>
                    </div>
                </div>
                <template v-if="codeArr.includes('code5')">
                    <highlight>
                        <pre>
&lt;!-- caption --&gt;
&lt;div class=&quot;table-responsive&quot;&gt;
  &lt;table&gt;
    &lt;thead&gt;
      &lt;tr&gt;
        &lt;th&gt;#&lt;/th&gt;
        &lt;th&gt;Name&lt;/th&gt;
        &lt;th&gt;Email&lt;/th&gt;
        &lt;th&gt;Status&lt;/th&gt;
        &lt;th class=&quot;text-center&quot;&gt;Register&lt;/th&gt;
      &lt;/tr&gt;
    &lt;/thead&gt;
    &lt;tbody&gt;
      &lt;template v-for=&quot;data in tableData&quot; :key=&quot;data.id&quot;&gt;
        &lt;tr&gt;
          &lt;td&gt;&#123;&#123; data.id &#125;&#125;&lt;/td&gt;
          &lt;td class=&quot;whitespace-nowrap&quot;&gt;&#123;&#123; data.name &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.email &#125;&#125;&lt;/td&gt;
          &lt;td&gt;
            &lt;span
              class=&quot;badge whitespace-nowrap&quot;
              :class=&quot;{
                'badge-outline-primary': data.status === 'Complete',
                'badge-outline-secondary': data.status === 'Pending',
                'badge-outline-info': data.status === 'In Progress',
                'badge-outline-danger': data.status === 'Canceled',
              }&quot;
              &gt;&#123;&#123; data.status &#125;&#125;&lt;/span
            &gt;
          &lt;/td&gt;
          &lt;td class=&quot;text-center&quot;&gt;&#123;&#123; data.register &#125;&#125;&lt;/td&gt;
        &lt;/tr&gt;
      &lt;/template&gt;
    &lt;/tbody&gt;
  &lt;/table&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref } from 'vue';
const tableData = ref([
  {
    id: 1,
    name: 'John Doe',
    email: 'johndoe@yahoo.com',
    date: '10/08/2020',
    sale: 120,
    status: 'Complete',
    register: '5 min ago',
    progress: '40%',
    position: 'Developer',
    office: 'London',
  },
  .....
]);
&lt;/script&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- progress table -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Progress Table</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code6')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        ></a
                    >
                </div>
                <div class="mb-5">
                    <div class="table-responsive">
                        <table>
                            <thead>
                                <tr>
                                    <th>#</th>
                                    <th>Name</th>
                                    <th>Progress</th>
                                    <th>Sales</th>
                                    <th class="text-center">Action</th>
                                </tr>
                            </thead>
                            <tbody>
                                <template v-for="data in tableData" :key="data.id">
                                    <tr>
                                        <td>{{ data.id }}</td>
                                        <td class="whitespace-nowrap">{{ data.name }}</td>
                                        <td>
                                            <div class="h-1.5 bg-[#ebedf2] dark:bg-dark/40 rounded-full flex w-full">
                                                <div
                                                    class="h-1.5 rounded-full rounded-bl-full text-center text-white text-xs"
                                                    :class="{
                                                        'bg-success': data.status === 'Complete',
                                                        'bg-secondary': data.status === 'Pending',
                                                        'bg-info': data.status === 'In Progress',
                                                        'bg-danger': data.status === 'Canceled',
                                                    }"
                                                    :style="`width: ${data.progress}`"
                                                ></div>
                                            </div>
                                        </td>
                                        <td
                                            class="whitespace-nowrap"
                                            :class="{
                                                'text-success': data.status === 'Complete',
                                                'text-secondary': data.status === 'Pending',
                                                'text-info': data.status === 'In Progress',
                                                'text-danger': data.status === 'Canceled',
                                            }"
                                        >
                                            {{ data.progress }}
                                        </td>
                                        <td class="p-3 border-b border-[#ebedf2] dark:border-[#191e3a] text-center">
                                            <div class="flex items-center">
                                                <div>
                                                    <button type="button" v-tippy:edit>
                                                        <icon-pencil class="ltr:mr-2 rtl:ml-2" />
                                                    </button>
                                                    <tippy target="edit">Edit</tippy>
                                                </div>
                                                <div>
                                                    <button type="button" v-tippy:delete>
                                                        <icon-trash-lines />
                                                    </button>
                                                    <tippy target="delete">Delete</tippy>
                                                </div>
                                            </div>
                                        </td>
                                    </tr>
                                </template>
                            </tbody>
                        </table>
                    </div>
                </div>
                <template v-if="codeArr.includes('code6')">
                    <highlight>
                        <pre>
&lt;!-- progress table --&gt;
&lt;div class=&quot;table-responsive&quot;&gt;
  &lt;table&gt;
    &lt;thead&gt;
      &lt;tr&gt;
        &lt;th&gt;#&lt;/th&gt;
        &lt;th&gt;Name&lt;/th&gt;
        &lt;th&gt;Progress&lt;/th&gt;
        &lt;th&gt;Sales&lt;/th&gt;
        &lt;th class=&quot;text-center&quot;&gt;Action&lt;/th&gt;
      &lt;/tr&gt;
    &lt;/thead&gt;
    &lt;tbody&gt;
      &lt;template v-for=&quot;data in tableData&quot; :key=&quot;data.id&quot;&gt;
        &lt;tr&gt;
          &lt;td&gt;&#123;&#123; data.id &#125;&#125;&lt;/td&gt;
          &lt;td class=&quot;whitespace-nowrap&quot;&gt;&#123;&#123; data.name &#125;&#125;&lt;/td&gt;
          &lt;td&gt;
            &lt;div class=&quot;h-1.5 bg-[#ebedf2] dark:bg-dark/40 rounded-full flex w-full&quot;&gt;
              &lt;div
                class=&quot;h-1.5 rounded-full rounded-bl-full text-center text-white text-xs&quot;
                :class=&quot;{
                  'bg-success': data.status === 'Complete',
                  'bg-secondary': data.status === 'Pending',
                  'bg-info': data.status === 'In Progress',
                  'bg-danger': data.status === 'Canceled',
                }&quot;
                :style=&quot;`width: ${data.progress}`&quot;
              &gt;&lt;/div&gt;
            &lt;/div&gt;
          &lt;/td&gt;
          &lt;td
            class=&quot;whitespace-nowrap&quot;
            :class=&quot;{
              'text-success': data.status === 'Complete',
              'text-secondary': data.status === 'Pending',
              'text-info': data.status === 'In Progress',
              'text-danger': data.status === 'Canceled',
            }&quot;
          &gt;
            &#123;&#123; data.progress &#125;&#125;
          &lt;/td&gt;
          &lt;td class=&quot;p-3 border-b border-[#ebedf2] dark:border-[#191e3a] text-center text-white-dark&quot;&gt;
            &lt;div class=&quot;flex items-center&quot;&gt;
              &lt;div&gt;
                &lt;button type=&quot;button&quot; v-tippy:edit&gt;
                  &lt;svg&gt; ... &lt;/svg&gt;
                &lt;/button&gt;
                &lt;tippy target=&quot;edit&quot;&gt;Edit&lt;/tippy&gt;
              &lt;/div&gt;
              &lt;div&gt;
                &lt;button type=&quot;button&quot; v-tippy:delete&gt;
                  &lt;svg&gt; ... &lt;/svg&gt;
                &lt;/button&gt;
                &lt;tippy target=&quot;delete&quot;&gt;Delete&lt;/tippy&gt;
              &lt;/div&gt;
            &lt;/div&gt;
          &lt;/td&gt;
        &lt;/tr&gt;
      &lt;/template&gt;
    &lt;/tbody&gt;
  &lt;/table&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref } from 'vue';
const tableData = ref([
  {
    id: 1,
    name: 'John Doe',
    email: 'johndoe@yahoo.com',
    date: '10/08/2020',
    sale: 120,
    status: 'Complete',
    register: '5 min ago',
    progress: '40%',
    position: 'Developer',
    office: 'London',
  },
  .....
]);
&lt;/script&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- Contextual -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Contextual</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code7')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        ></a
                    >
                </div>
                <div class="mb-5">
                    <div class="table-responsive">
                        <table>
                            <thead>
                                <tr>
                                    <th>#</th>
                                    <th>First Name</th>
                                    <th>Last Name</th>
                                    <th>Email</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr class="bg-dark-dark-light border-dark-dark-light">
                                    <td>1</td>
                                    <td>John</td>
                                    <td>Doe</td>
                                    <td>johndoe@yahoo.com</td>
                                </tr>
                                <tr class="bg-primary/20 border-primary/20">
                                    <td>2</td>
                                    <td>Andy</td>
                                    <td>King</td>
                                    <td>andyking@gmail.com</td>
                                </tr>
                                <tr class="bg-secondary/20 border-secondary/20">
                                    <td>3</td>
                                    <td>Lisa</td>
                                    <td>Doe</td>
                                    <td>lisadoe@yahoo.com</td>
                                </tr>
                                <tr class="bg-success/20 border-success/20">
                                    <td>4</td>
                                    <td>Vincent</td>
                                    <td>Carpenter</td>
                                    <td>vinnyc@yahoo.com</td>
                                </tr>
                                <tr class="bg-dark-dark-light border-dark-dark-light">
                                    <td>5</td>
                                    <td>Amy</td>
                                    <td>Diaz</td>
                                    <td>amydiaz@yahoo.com</td>
                                </tr>
                                <tr class="bg-danger/20 border-danger/20">
                                    <td>6</td>
                                    <td>Nia</td>
                                    <td>Hillyer</td>
                                    <td>niahill@gmail.com</td>
                                </tr>
                                <tr class="bg-info/20 border-info/20">
                                    <td>7</td>
                                    <td>Marry</td>
                                    <td>McDonald</td>
                                    <td>marryMcD@yahoo.com</td>
                                </tr>
                                <tr class="bg-warning/20 border-warning/20">
                                    <td>8</td>
                                    <td>Shaun</td>
                                    <td>Park</td>
                                    <td>park@yahoo.com</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>

                <template v-if="codeArr.includes('code7')">
                    <highlight>
                        <pre>
&lt;!-- contextual --&gt;
&lt;div class=&quot;table-responsive&quot;&gt;
  &lt;table&gt;
    &lt;thead&gt;
      &lt;tr&gt;
        &lt;th&gt;#&lt;/th&gt;
        &lt;th&gt;First Name&lt;/th&gt;
        &lt;th&gt;Last Name&lt;/th&gt;
        &lt;th&gt;Email&lt;/th&gt;
      &lt;/tr&gt;
    &lt;/thead&gt;
    &lt;tbody&gt;
      &lt;tr class=&quot;bg-dark-dark-light border-dark-dark-light&quot;&gt;
        &lt;td&gt;1&lt;/td&gt;
        &lt;td&gt;John&lt;/td&gt;
        &lt;td&gt;Doe&lt;/td&gt;
        &lt;td&gt;johndoe@yahoo.com&lt;/td&gt;
      &lt;/tr&gt;
      &lt;tr class=&quot;bg-primary/20 border-primary/20&quot;&gt;
        &lt;td&gt;2&lt;/td&gt;
        &lt;td&gt;Andy&lt;/td&gt;
        &lt;td&gt;King&lt;/td&gt;
        &lt;td&gt;andyking@gmail.com&lt;/td&gt;
      &lt;/tr&gt;
      &lt;tr class=&quot;bg-secondary/20 border-secondary/20&quot;&gt;
        &lt;td&gt;3&lt;/td&gt;
        &lt;td&gt;Lisa&lt;/td&gt;
        &lt;td&gt;Doe&lt;/td&gt;
        &lt;td&gt;lisadoe@yahoo.com&lt;/td&gt;
      &lt;/tr&gt;
      &lt;tr class=&quot;bg-success/20 border-success/20&quot;&gt;
        &lt;td&gt;4&lt;/td&gt;
        &lt;td&gt;Vincent&lt;/td&gt;
        &lt;td&gt;Carpenter&lt;/td&gt;
        &lt;td&gt;vinnyc@yahoo.com&lt;/td&gt;
      &lt;/tr&gt;
      &lt;tr class=&quot;bg-dark-dark-light border-dark-dark-light&quot;&gt;
        &lt;td&gt;5&lt;/td&gt;
        &lt;td&gt;Amy&lt;/td&gt;
        &lt;td&gt;Diaz&lt;/td&gt;
        &lt;td&gt;amydiaz@yahoo.com&lt;/td&gt;
      &lt;/tr&gt;
      &lt;tr class=&quot;bg-danger/20 border-danger/20&quot;&gt;
        &lt;td&gt;6&lt;/td&gt;
        &lt;td&gt;Nia&lt;/td&gt;
        &lt;td&gt;Hillyer&lt;/td&gt;
        &lt;td&gt;niahill@gmail.com&lt;/td&gt;
      &lt;/tr&gt;
      &lt;tr class=&quot;bg-info/20 border-info/20&quot;&gt;
        &lt;td&gt;7&lt;/td&gt;
        &lt;td&gt;Marry&lt;/td&gt;
        &lt;td&gt;McDonald&lt;/td&gt;
        &lt;td&gt;marryMcD@yahoo.com&lt;/td&gt;
      &lt;/tr&gt;
      &lt;tr class=&quot;bg-warning/20 border-warning/20&quot;&gt;
        &lt;td&gt;8&lt;/td&gt;
        &lt;td&gt;Shaun&lt;/td&gt;
        &lt;td&gt;Park&lt;/td&gt;
        &lt;td&gt;park@yahoo.com&lt;/td&gt;
      &lt;/tr&gt;
    &lt;/tbody&gt;
  &lt;/table&gt;
&lt;/div&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- dropdown -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Dropdown</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code8')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code
                        </span></a
                    >
                </div>
                <div class="mb-5">
                    <div class="table-responsive">
                        <table>
                            <thead>
                                <tr>
                                    <th>Name</th>
                                    <th>Date</th>
                                    <th>Sale</th>
                                    <th>Status</th>
                                    <th class="text-center">Action</th>
                                </tr>
                            </thead>
                            <tbody>
                                <template v-for="data in tableData" :key="data.id">
                                    <tr>
                                        <td class="whitespace-nowrap">{{ data.name }}</td>
                                        <td>{{ data.date }}</td>
                                        <td>{{ data.sale }}</td>
                                        <td>
                                            <span
                                                class="badge whitespace-nowrap"
                                                :class="{
                                                    'bg-primary': data.status === 'Complete',
                                                    'bg-secondary': data.status === 'Pending',
                                                    'bg-success': data.status === 'In Progress',
                                                    'bg-danger': data.status === 'Canceled',
                                                }"
                                                >{{ data.status }}</span
                                            >
                                        </td>
                                        <td class="text-center">
                                            <div class="dropdown">
                                                <Popper
                                                    :placement="store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'"
                                                    offsetDistance="0"
                                                    class="align-middle"
                                                >
                                                    <a href="javascript:;">
                                                        <icon-horizontal-dots class="opacity-70 m-auto" />
                                                    </a>
                                                    <template #content="{ close }">
                                                        <ul @click="close()">
                                                            <li>
                                                                <a href="javascript:;">Download</a>
                                                            </li>
                                                            <li>
                                                                <a href="javascript:;">Share</a>
                                                            </li>
                                                            <li>
                                                                <a href="javascript:;">Edit</a>
                                                            </li>
                                                            <li>
                                                                <a href="javascript:;">Delete</a>
                                                            </li>
                                                        </ul>
                                                    </template>
                                                </Popper>
                                            </div>
                                        </td>
                                    </tr>
                                </template>
                            </tbody>
                        </table>
                    </div>
                </div>
                <template v-if="codeArr.includes('code8')">
                    <highlight>
                        <pre>
&lt;!-- dropdown --&gt;
&lt;div class=&quot;table-responsive&quot;&gt;
  &lt;table&gt;
    &lt;thead&gt;
      &lt;tr&gt;
        &lt;th&gt;Name&lt;/th&gt;
        &lt;th&gt;Date&lt;/th&gt;
        &lt;th&gt;Sale&lt;/th&gt;
        &lt;th&gt;Status&lt;/th&gt;
        &lt;th class=&quot;text-center&quot;&gt;Action&lt;/th&gt;
      &lt;/tr&gt;
    &lt;/thead&gt;
    &lt;tbody&gt;
      &lt;template v-for=&quot;data in tableData&quot; :key=&quot;data.id&quot;&gt;
        &lt;tr&gt;
          &lt;td class=&quot;whitespace-nowrap&quot;&gt;&#123;&#123; data.name &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.date &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.sale &#125;&#125;&lt;/td&gt;
          &lt;td&gt;
            &lt;span
              class=&quot;badge whitespace-nowrap&quot;
              :class=&quot;{
                'bg-primary': data.status === 'Complete',
                'bg-secondary': data.status === 'Pending',
                'bg-success': data.status === 'In Progress',
                'bg-danger': data.status === 'Canceled',
              }&quot;
              &gt;&#123;&#123; data.status &#125;&#125;&lt;/span
            &gt;
          &lt;/td&gt;
          &lt;td class=&quot;text-center&quot;&gt;
            &lt;div class=&quot;dropdown&quot;&gt;
              &lt;Popper :placement=&quot;store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'&quot; offsetDistance=&quot;0&quot; class=&quot;align-middle&quot;&gt;
                &lt;a href=&quot;javascript:;&quot;&gt;
                  &lt;svg&gt; ... &lt;/svg&gt;
                &lt;/a&gt;
                &lt;template #content=&quot;{ close }&quot;&gt;
                  &lt;ul @click=&quot;close()&quot;&gt;
                    &lt;li&gt;
                      &lt;a href=&quot;javascript:;&quot;&gt;Download&lt;/a&gt;
                    &lt;/li&gt;
                    &lt;li&gt;
                      &lt;a href=&quot;javascript:;&quot;&gt;Share&lt;/a&gt;
                    &lt;/li&gt;
                    &lt;li&gt;
                      &lt;a href=&quot;javascript:;&quot;&gt;Edit&lt;/a&gt;
                    &lt;/li&gt;
                    &lt;li&gt;
                      &lt;a href=&quot;javascript:;&quot;&gt;Delete&lt;/a&gt;
                    &lt;/li&gt;
                  &lt;/ul&gt;
                &lt;/template&gt;
              &lt;/Popper&gt;
            &lt;/div&gt;
          &lt;/td&gt;
        &lt;/tr&gt;
      &lt;/template&gt;
    &lt;/tbody&gt;
  &lt;/table&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref } from 'vue';
const tableData = ref([
  {
    id: 1,
    name: 'John Doe',
    email: 'johndoe@yahoo.com',
    date: '10/08/2020',
    sale: 120,
    status: 'Complete',
    register: '5 min ago',
    progress: '40%',
    position: 'Developer',
    office: 'London',
  },
  .....
]);
&lt;/script&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- table with footer -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Table with Footer</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code9')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        ></a
                    >
                </div>
                <div class="mb-5">
                    <div class="table-responsive">
                        <table>
                            <thead>
                                <tr>
                                    <th>Name</th>
                                    <th>Position</th>
                                    <th>Office</th>
                                    <th class="!text-center">Action</th>
                                </tr>
                            </thead>
                            <tbody>
                                <template v-for="data in tableData" :key="data.id">
                                    <tr>
                                        <td class="whitespace-nowrap">{{ data.name }}</td>
                                        <td>{{ data.position }}</td>
                                        <td>{{ data.office }}</td>
                                        <td class="text-center">
                                            <ul class="flex items-center justify-center gap-2">
                                                <li>
                                                    <a href="javascript:;" v-tippy:edit>
                                                        <icon-circle-check class="w-5 h-5 text-primary" />
                                                    </a>
                                                    <tippy target="edit">Edit</tippy>
                                                </li>
                                                <li>
                                                    <a href="javascript:;" v-tippy:delete>
                                                        <icon-x-circle class="text-danger" />
                                                    </a>
                                                    <tippy target="delete">Delete</tippy>
                                                </li>
                                            </ul>
                                        </td>
                                    </tr>
                                </template>
                            </tbody>
                            <tfoot>
                                <tr>
                                    <th>Name</th>
                                    <th>Position</th>
                                    <th>Office</th>
                                    <th class="!text-center">Action</th>
                                </tr>
                            </tfoot>
                        </table>
                    </div>
                </div>
                <template v-if="codeArr.includes('code9')">
                    <highlight>
                        <pre>
&lt;!-- table with footer --&gt;
&lt;div class=&quot;table-responsive&quot;&gt;
  &lt;table&gt;
    &lt;thead&gt;
      &lt;tr&gt;
        &lt;th&gt;Name&lt;/th&gt;
        &lt;th&gt;Position&lt;/th&gt;
        &lt;th&gt;Office&lt;/th&gt;
        &lt;th class=&quot;!text-center&quot;&gt;Action&lt;/th&gt;
      &lt;/tr&gt;
    &lt;/thead&gt;
    &lt;tbody&gt;
      &lt;template v-for=&quot;data in tableData&quot; :key=&quot;data.id&quot;&gt;
        &lt;tr&gt;
          &lt;td class=&quot;whitespace-nowrap&quot;&gt;&#123;&#123; data.name &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.position &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.office &#125;&#125;&lt;/td&gt;
          &lt;td class=&quot;text-center&quot;&gt;
            &lt;ul class=&quot;flex items-center justify-center gap-2&quot;&gt;
              &lt;li&gt;
                &lt;a href=&quot;javascript:;&quot; v-tippy:edit&gt;
                  &lt;svg&gt; ... &lt;/svg&gt;
                &lt;/a&gt;
                &lt;tippy target=&quot;edit&quot;&gt;Edit&lt;/tippy&gt;
              &lt;/li&gt;
              &lt;li&gt;
                &lt;a href=&quot;javascript:;&quot; v-tippy:delete&gt;
                  &lt;svg&gt; ... &lt;/svg&gt;
                &lt;/a&gt;
                &lt;tippy target=&quot;delete&quot;&gt;Delete&lt;/tippy&gt;
              &lt;/li&gt;
            &lt;/ul&gt;
          &lt;/td&gt;
        &lt;/tr&gt;
      &lt;/template&gt;
    &lt;/tbody&gt;
    &lt;tfoot&gt;
      &lt;tr&gt;
        &lt;th&gt;Name&lt;/th&gt;
        &lt;th&gt;Position&lt;/th&gt;
        &lt;th&gt;Office&lt;/th&gt;
        &lt;th class=&quot;!text-center&quot;&gt;Action&lt;/th&gt;
      &lt;/tr&gt;
    &lt;/tfoot&gt;
  &lt;/table&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref } from 'vue';
const tableData = ref([
  {
    id: 1,
    name: 'John Doe',
    email: 'johndoe@yahoo.com',
    date: '10/08/2020',
    sale: 120,
    status: 'Complete',
    register: '5 min ago',
    progress: '40%',
    position: 'Developer',
    office: 'London',
  },
  .....
]);
&lt;/script&gt;
</pre
                        >
                    </highlight>
                </template>
            </div>

            <!-- checkboxes -->
            <div class="panel">
                <div class="flex items-center justify-between mb-5">
                    <h5 class="font-semibold text-lg dark:text-white-light">Checkboxes</h5>
                    <a class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600" href="javascript:;" @click="toggleCode('code10')"
                        ><span class="flex items-center">
                            <icon-code class="me-2" />
                            Code</span
                        ></a
                    >
                </div>
                <div class="mb-5">
                    <div class="table-responsive">
                        <table>
                            <thead>
                                <tr>
                                    <th><input type="checkbox" class="form-checkbox" /></th>
                                    <th>Name</th>
                                    <th>Date</th>
                                    <th>Sale</th>
                                    <th class="!text-center">Action</th>
                                </tr>
                            </thead>
                            <tbody>
                                <template v-for="data in tableData" :key="data.id">
                                    <tr>
                                        <td><input type="checkbox" class="form-checkbox" /></td>
                                        <td class="whitespace-nowrap">{{ data.name }}</td>
                                        <td>{{ data.date }}</td>
                                        <td>{{ data.sale }}</td>
                                        <td class="text-center">
                                            <ul class="flex items-center justify-center gap-2">
                                                <li>
                                                    <a href="javascript:;" v-tippy:settings>
                                                        <icon-settings class="w-5 h-5 text-primary" />
                                                    </a>
                                                    <tippy target="settings">Settings</tippy>
                                                </li>
                                                <li>
                                                    <a href="javascript:;" v-tippy:edit>
                                                        <icon-pencil class="text-success" />
                                                    </a>
                                                    <tippy target="edit">Edit</tippy>
                                                </li>
                                                <li>
                                                    <a href="javascript:;" v-tippy:delete>
                                                        <icon-trash-lines class="text-danger" />
                                                    </a>
                                                    <tippy target="delete">Delete</tippy>
                                                </li>
                                            </ul>
                                        </td>
                                    </tr>
                                </template>
                            </tbody>
                        </table>
                    </div>
                </div>
                <template v-if="codeArr.includes('code10')">
                    <highlight>
                        <pre>
&lt;!-- dropdown --&gt;
&lt;div class=&quot;table-responsive&quot;&gt;
  &lt;table&gt;
    &lt;thead&gt;
      &lt;tr&gt;
        &lt;th&gt;&lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox&quot; /&gt;&lt;/th&gt;
        &lt;th&gt;Name&lt;/th&gt;
        &lt;th&gt;Date&lt;/th&gt;
        &lt;th&gt;Sale&lt;/th&gt;
        &lt;th class=&quot;!text-center&quot;&gt;Action&lt;/th&gt;
      &lt;/tr&gt;
    &lt;/thead&gt;
    &lt;tbody&gt;
      &lt;template v-for=&quot;data in tableData&quot; :key=&quot;data.id&quot;&gt;
        &lt;tr&gt;
          &lt;td&gt;&lt;input type=&quot;checkbox&quot; class=&quot;form-checkbox&quot; /&gt;&lt;/td&gt;
          &lt;td class=&quot;whitespace-nowrap&quot;&gt;&#123;&#123; data.name &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.date &#125;&#125;&lt;/td&gt;
          &lt;td&gt;&#123;&#123; data.sale &#125;&#125;&lt;/td&gt;
          &lt;td class=&quot;text-center&quot;&gt;
            &lt;ul class=&quot;flex items-center justify-center gap-2&quot;&gt;
              &lt;li&gt;
                &lt;a href=&quot;javascript:;&quot; v-tippy:settings&gt; &lt;svg&gt; ... &lt;/svg&gt;&lt;/a&gt;
                &lt;tippy target=&quot;settings&quot;&gt;Edit&lt;/tippy&gt;
              &lt;/li&gt;
              &lt;li&gt;
                &lt;a href=&quot;javascript:;&quot; v-tippy:edit&gt; &lt;svg&gt; ... &lt;/svg&gt;&lt;/a&gt;
                &lt;tippy target=&quot;edit&quot;&gt;Edit&lt;/tippy&gt;
              &lt;/li&gt;
              &lt;li&gt;
                &lt;a href=&quot;javascript:;&quot; v-tippy:delete&gt; &lt;svg&gt; ... &lt;/svg&gt;&lt;/a&gt;
                &lt;tippy target=&quot;delete&quot;&gt;Edit&lt;/tippy&gt;
              &lt;/li&gt;
            &lt;/ul&gt;
          &lt;/td&gt;
        &lt;/tr&gt;
      &lt;/template&gt;
    &lt;/tbody&gt;
  &lt;/table&gt;
&lt;/div&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
import { ref } from 'vue';
const tableData = ref([
  {
    id: 1,
    name: 'John Doe',
    email: 'johndoe@yahoo.com',
    date: '10/08/2020',
    sale: 120,
    status: 'Complete',
    register: '5 min ago',
    progress: '40%',
    position: 'Developer',
    office: 'London',
  },
  .....
]);
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
    import { useAppStore } from '@/stores/index';
    import { useMeta } from '@/composables/use-meta';

    import IconCode from '@/components/icon/icon-code.vue';
    import IconTrashLines from '@/components/icon/icon-trash-lines.vue';
    import IconXCircle from '@/components/icon/icon-x-circle.vue';
    import IconPencil from '@/components/icon/icon-pencil.vue';
    import IconHorizontalDots from '@/components/icon/icon-horizontal-dots.vue';
    import IconCircleCheck from '@/components/icon/icon-circle-check.vue';
    import IconSettings from '@/components/icon/icon-settings.vue';

    useMeta({ title: 'Tables' });

    const store = useAppStore();

    const { codeArr, toggleCode } = codePreview();
    const tableData = ref([
        {
            id: 1,
            name: 'John Doe',
            email: 'johndoe@yahoo.com',
            date: '10/08/2020',
            sale: 120,
            status: 'Complete',
            register: '5 min ago',
            progress: '40%',
            position: 'Developer',
            office: 'London',
        },
        {
            id: 2,
            name: 'Shaun Park',
            email: 'shaunpark@gmail.com',
            date: '11/08/2020',
            sale: 400,
            status: 'Pending',
            register: '11 min ago',
            progress: '23%',
            position: 'Designer',
            office: 'New York',
        },
        {
            id: 3,
            name: 'Alma Clarke',
            email: 'alma@gmail.com',
            date: '12/02/2020',
            sale: 310,
            status: 'In Progress',
            register: '1 hour ago',
            progress: '80%',
            position: 'Accountant',
            office: 'Amazon',
        },
        {
            id: 4,
            name: 'Vincent Carpenter',
            email: 'vincent@gmail.com',
            date: '13/08/2020',
            sale: 100,
            status: 'Canceled',
            register: '1 day ago',
            progress: '60%',
            position: 'Data Scientist',
            office: 'Canada',
        },
    ]);
</script>
