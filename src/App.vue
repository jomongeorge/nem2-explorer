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
  <div id="app">
    <top-header />
    <page-menu />
    <router-view :key="$route.fullPath"/>
    <page-footer/>
  </div>
</template>
<script>

export default {
  data: () => {
    return {
      info: 1
    }
  },
  created() {
    this.initialize()
  },
  destroyed() {
    this.uninitialize()
  },
  methods: {
    initialize() {
      this.$store.dispatch('initialize')
        .catch(error => console.log(error))
    },
    uninitialize() {
      this.$store.dispatch('uninitialize')
    }
  }
}
</script>

<style lang="scss">
#app{
  // width: 100vw;
  // height: 100vh;
}

.noselect{
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  outline: 0;
}

.pointer{
  cursor: pointer;
}
</style>
