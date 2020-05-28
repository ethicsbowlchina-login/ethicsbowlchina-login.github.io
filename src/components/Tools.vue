/*!
 * Copyright (c) 2018, Okta, Inc. and/or its affiliates. All rights reserved.
 * The Okta software accompanied by this notice is provided pursuant to the Apache License, Version 2.0 (the "License.")
 *
 * You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0.
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
 * WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 *
 * See the License for the specific language governing permissions and limitations under the License.
 */

<template>
  <div class="tools">
    <h1 class="ui header">
      Tools
    </h1>
    <p>
      Below is a list of tools. Please feel free to access.
    </p>
    <h3><center>You might need VPN tools to run this website properly.</center></h3>
    <br>
    <br>
    <br>
    <h2><center>Coin Flipper</center></h2>
    <iframe id="oak-embed" width="100%" height="100%" scrolling="no" frameborder="0" src="https://justflipacoin.com/?c=white"></iframe>
    <br>
    <br>
    <br>
    <h2><center>Ethics Bowl Timer</center></h2>
    <iframe id="oak-embed" width="100%" height="100%" frameborder="0" src="https://embed-timer.onlinealarmkur.com/en/"></iframe>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <h2><center>Random Match Assignment Tool</center></h2>
    <iframe id="oak-embed" width="100%" height="100%" frameborder="0" src="http://chir.ag/projects/team-maker/"></iframe>
    <br>
    <br>
    <br>
    <br>
    <br>
    <br>
    <h2><center>Scoring System</center></h2>
    <iframe width="100%" height="100%" frameborder="0" src="https://docs.google.com/spreadsheets/d/1908gzrUqw4JL2qh2iFEzjpyaYEBuOqZm5sAtG0Ki9rs/edit?usp=sharing"></iframe>
  </div>
</template>

<script>
export default {
  name: 'Tools',
  data () {
    return {
      claims: []
    }
  },
  async created () {
    this.claims = await Object.entries(await this.$auth.getUser()).map(entry => ({ claim: entry[0], value: entry[1] }))
  }
}
</script>
