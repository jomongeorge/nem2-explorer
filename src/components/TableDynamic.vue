/*
 *
 * Copyright (c) 2019-present for NEM
 *
 * Licensed under the Apache License, Version 2.0 (the "License ");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 *
 *     http://www.apache.org/licenses/LICENSE-2.0
 *
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 *
 */

<template>
  <div>
    <div class="table-responsive">
      <div class="dataTables_wrapper container-fluid dt-bootstrap4 no-footer p-0">
        <table
          id="table-dynmic"
          class="table table-striped table-bordered"
          v-bind:class="tableClass"
          cellspacing="0"
          width="100%"
        >
          <thead>
            <tr>
              <th
                v-for="(item,index) in tableHead"
                v-bind:key="index"
              >
                {{item}}
              </th>
            </tr>
          </thead>
          <tbody>
            <tr
              v-for="(item,index) in tableData"
              v-bind:key="index"
            >
              <td
                v-for="(subitem,idx) in item"
                v-bind:key="idx"
                v-html="formatData(subitem)"
              />
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    tableClass: String,
    tableHead: Array,
    tableData: Array,
    tableRowAction: { type: Function }
  },
  methods: {
    formatData(data) {
      // check data is HTML
      return data
    }
  }
}
</script>
