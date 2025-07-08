<template>
  <div class="register-notice-page">
    <div class="notice-card">
      <h2 class="title">用户注册须知</h2>

      <div class="content">
        <p class="greeting">尊敬的用户：</p>
        <p>欢迎注册并使用国家无人驾驶航空器一体化综合监管服务平台（民用无人驾驶航空器综合管理平台）。</p>

        <h3>一、注册</h3>
        <ol class="step-list">
          <li>步骤1，阅读用户注册须知。</li>
          <li>
            步骤2，注册账号信息。
            <p>
              根据系统提示，填写登录账号、登录密码、确认密码、手机号码、电子邮箱等信息，个人用户选择用户类型为个人，单位用户选择用户类型为单位。
            </p>
          </li>
          <li>
            步骤3，完善账号信息。
            <ol class="sub-list">
              <li>个人用户：完善个人信息，包括姓名、性别、证件类型、证件号码、居住地址等。</li>
              <li>单位用户：完善单位信息，包括单位名称、统一社会信用代码、法人代表名称、注册人、注册地址等。</li>
            </ol>
          </li>
        </ol>

        <h3>二、责任</h3>
        <ol class="step-list">
          <li>用户须遵守国家法律法规。</li>
          <li>
            用户应按中国民用航空局相关要求填写真实准确的个人资料或单位资料，如用户提供的资料包含有不正确的信息，本平台保留结束用户使用相关服务的权利。
          </li>
          <li>用户注册成功后，账号和密码由用户负责保管；用户应对以其用户账号进行的所有活动和事件负法律责任。</li>
          <li>
            保护用户隐私是本平台的一项基本政策，本平台保证不对外公开或向第三方提供用户注册资料及用户在使用本平台提供服务时存储在本平台的非公开内容，除下列情况外：
            <ol class="sub-list alpha-list">
              <li>事先获得用户的明确授权；</li>
              <li>根据有关的法律法规要求；</li>
              <li>按相关政府主管部门的要求；</li>
              <li>为维护社会公众的利益；</li>
            </ol>
          </li>
        </ol>
      </div>

      <div class="footer">
        <label class="agree-label">
          <input type="checkbox" v-model="accepted" />
          我已阅读并接受上述内容
        </label>
        <button class="next-button" :disabled="!accepted">下一步</button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

/**
 * 是否已阅读并接受
 */
const accepted = ref(false)
</script>

<style scoped>
.register-notice-page {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #e2e8f0; /* Tailwind slate-200 style */
  padding: 24px;
  box-sizing: border-box;
}

.notice-card {
  width: 100%;
  max-width: 900px;
  background-color: #f8fafc; /* very light */
  border: 1px solid #cbd5e1;
  border-radius: 16px;
  padding: 32px 48px;
  box-sizing: border-box;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
}

.title {
  text-align: center;
  font-size: 24px;
  font-weight: 600;
  margin-bottom: 24px;
}

.content {
  font-size: 14px;
  line-height: 1.6;
  color: #1e293b;
  max-height: 420px;
  overflow-y: auto;
  padding-right: 8px; /* space for scrollbar */
}

.greeting {
  font-weight: 600;
}

h3 {
  margin-top: 16px;
  margin-bottom: 8px;
  font-weight: 600;
}

.step-list {
  list-style-type: decimal;
  padding-left: 20px;
}

.sub-list {
  list-style-type: decimal;
  padding-left: 20px;
  margin-top: 8px;
}

.alpha-list {
  list-style-type: lower-alpha;
}

.footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 24px;
  flex-wrap: wrap;
}

.agree-label {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 14px;
  user-select: none;
}

.next-button {
  background-color: #3b82f6; /* blue-500 */
  border: none;
  border-radius: 6px;
  padding: 8px 24px;
  color: #fff;
  font-size: 14px;
  cursor: pointer;
  transition: opacity 0.2s ease;
}

.next-button[disabled] {
  opacity: 0.4;
  cursor: not-allowed;
}
</style>