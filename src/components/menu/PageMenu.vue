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
  <header class="ex-header bg01">
    <div class="container p-0">
      <div class="row flex-nowrap justify-content-between align-items-center">
        <a href="#" class="mobilemenu" @click="showTopMenu = !showTopMenu">
          <i class="ico-navicon-round"></i>
        </a>
        <div class="col-md-1 logo-wrap">
          <router-link to="/" class="logo-h">
            <img src="theme/img/logo-w.png" alt="Nem" />
          </router-link>
        </div>
        <div class="col-md-11">
          <div class="nav-con" v-bind:class="{'nav-active':(showTopMenu==1)}">
            <ul class="nav-menu ls1">
              <PageMenuItem
                :to="item.to"
                :text="item.text"
                :classname="item.classname"
                v-for="item in items"
                v-bind:key="item.text"
              />
            </ul>
          </div>
        </div>
        <!-- <div class="col-md-3 lang-swtchwrap">
                    <div class="lang-swtch dropdown ">
                        <a class="dropdown-toggle"><i class="flag-icon fl-i-us"></i>English</a>
                        <div class="dropdown-menu dropdown-menu-right">
                            <a class="dropdown-item active" href="#"><i class="flag-icon fl-i-us"></i>English</a>
                            <a class="dropdown-item" href="#"><i class="flag-icon fl-i-jp"></i>日本語</a>
                        </div>
                    </div>
        </div>-->
      </div>
    </div>
  </header>
</template>
<script>
import w1 from './PageMenuItem.vue'
import { pageMenu } from '../../config/'
export default {
  name: 'PageMenu',
  components: {
    PageMenuItem: w1
  },
  props: {
    msg: String
  },
  data() {
    return {
      showTopMenu: false,
      items: pageMenu.items
    }
  }
}
</script>
