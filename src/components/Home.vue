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
  <div id="home">
    <h1 class="ui header">Welcome to Ethics Bowl China Online App!</h1>
    <div v-if="!this.$parent.authenticated">
      <p>Thank you for joining the Ethics Bowl China!</p>
      <p><b>For participants, this platform provides access to premium resources designed for you to: </b></p>
      <p>1. Be better prepared for the Ethics Bowl.</p>
      <p>2. Learn ethical theories and applied ethics.</p>
      <p>3. Organize philosophical discussions for an Ethics Bowl club or any philosophy club!</p>
      <p><b>These materials are free of charge for all participants of any Ethics Bowl China event!</b></p>
      <p><b>For organizers, moderators, and volunteers, this platform is a collection of tools specially designed for Ethics Bowl China events. They include:</b></p>
      <p>1. Random Match Assignment Tool</p>
      <p>2. Scorekeeping Tool</p>
      <p>3. Ethics Bowl China Timer</p>
      <p>Note: You might need a VPN to ensure high connection speed.</p>
      <p>App developed by Leo Huang.</p>
      <button
        id="login-button"
        class="ui primary button"
        role="button"
        v-on:click="login()"
      >
      Login
      </button>
    </div>

    <div v-if="this.$parent.authenticated">
      <p>Welcome back, {{claims.name}}!</p>
      <p><b>
        You have successfully signed in to the Ethics Bowl China Online App.
        Thank you for registering for an Ethics Bowl China event!
      </b></p>
      <p><b>For participants, this platform provides access to <a href="/resources">premium resources</a> designed for you to: </b></p>
      <p>1. Be better prepared for the Ethics Bowl.</p>
      <p>2. Learn ethical theories and applied ethics.</p>
      <p>3. Organize philosophical discussions for an Ethics Bowl club or any philosophy club!</p>
      <p>These materials are free of charge for all participants of any Ethics Bowl China event!</p>
      <p>Click <a href="/resources">here</a> to access the premium resources.</p>
      <p><b>For organizers, moderators, and volunteers, this platform is <a href="/tools">a collection of tools</a> specially designed for Ethics Bowl China events. They include:</b></p>
      <p>1. Random Match Assignment Tool</p>
      <p>2. Scorekeeping Tool</p>
      <p>3. Ethics Bowl China Timer</p>
      <p>Click <a href="/tools">here</a> to access these useful tools for Ethics Bowl China events.</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'home',
  data: function () {
    return {
      claims: '',
      resourceServerExamples: [
        {
          label: 'Node/Express Resource Server Example',
          url: 'https://github.com/okta/samples-nodejs-express-4/tree/master/resource-server'
        },
        {
          label: 'Java/Spring MVC Resource Server Example',
          url: 'https://github.com/okta/samples-java-spring-mvc/tree/master/resource-server'
        }
      ]
    }
  },
  created () { this.setup() },
  methods: {
    async setup () {
      this.claims = await this.$auth.getUser()
    },
    login () {
      this.$auth.loginRedirect('/')
    }
  }
}
</script>
