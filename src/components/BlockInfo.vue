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
<div class="blk-info">
  <div class="inrw">
    <span>{{ item.numTransactions }} Transactions</span>
    <Age :date="item.date"/>
  </div>
  <div class="inrw flex">
    <span>Harvester</span>
    <AddressLink :address="item.signer.address.address" class="acnt"/>
  </div>
</div>
</template>
<script>
import w1 from '@/components/Age.vue'
import w2 from '@/components/AddressLink.vue'

export default {
  name: 'BlockInfo',
  components: {
    Age: w1,
    AddressLink: w2
  },
  props: {
    item: {}
  }
}
</script>
