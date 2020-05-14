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
  <div class="resources">
    <h1 class="ui header">
      Premium Resources
    </h1>
    <p>
      Below is a list of premium resources. Please feel free to access.
    </p>
    <p>
      <a href="https://drive.google.com/drive/folders/1AD-k77IDCuA1S6DlI3OBmgIfdbyLiaIK?usp=sharing">PowerPoints: Ethical Theories and Applied Ethics</a>
      <a href="https://drive.google.com/drive/folders/1yqsQ6SSVnQQgNGEUXcb1h105qxycRG-i?usp=sharing">Philosophy Club Discussion Topics and Readings</a>
      <a href="https://drive.google.com/drive/folders/1lIG6fmQsW_8i5cT2CYMIelIlm3IrQvud?usp=sharing">How to Organize Philosophical Discussions</a>
    </p>
  </div>
</template>

<script>
export default {
  name: 'Resources',
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
