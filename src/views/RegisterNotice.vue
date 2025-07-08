<template>
  <div class="register-notice-container">
    <div class="card">
      <h2 class="title">用户注册须知</h2>

      <p class="greeting">尊敬的用户：</p>
      <p>
        欢迎您注册并使用国家无人驾驶航空器一体化综合监控服务平台
        （民用无人驾驶航空器综合管理平台）。
      </p>

      <!-- 一、注册 -->
      <section>
        <h3>一、注册</h3>
        <ol class="section-list">
          <li>步骤 1，阅读用户注册须知。</li>
          <li>步骤 2，注册账号信息。
            <p class="indent">
              根据系统提示，填写登录账号、登录密码、确认密码、手机号、电子邮箱等信息，个人用户选择用户类型为个人，单位用户选择用户类型为单位。
            </p>
          </li>
          <li>步骤 3，完善账号信息。
            <p class="indent">1）个人用户：完善个人信息，包括姓名、性别、证件类型、证件号码、居住地址等。</p>
            <p class="indent">2）单位用户：完善单位信息，包括单位名称、统一社会信用代码、法人代表名称、注册人、注册地址等。</p>
          </li>
        </ol>
      </section>

      <!-- 二、责任 -->
      <section>
        <h3>二、责任</h3>
        <ol class="section-list">
          <li>用户须遵守国家法律法规。</li>
          <li>用户须按中国民用航空局相关要求填写真实准确的个人资料或单位资料，如用户提供的资料包含有不正确的信息，本平台保留结束用户使用相关服务的权利。</li>
          <li>用户注册成功后，账号和密码由用户负责保管；用户应对以其用户账号进行的所有活动和事件负法律责任。</li>
          <li>
            保护用户隐私是本平台的一项基本政策，本平台保证不对外公开或向第三方提供用户注册资料及用户在使用本平台提供服务时存储在本平台的非公开内容，但下列情况除外：
            <ul class="sub-list">
              <li>a）事先获得用户的明确授权；</li>
              <li>b）根据有关的法律法规要求；</li>
              <li>c）按照相关政府主管部门的要求；</li>
              <li>d）为维护社会公众的利益；</li>
            </ul>
          </li>
        </ol>
      </section>

      <!-- 底部操作 -->
      <div class="footer">
        <label class="checkbox-wrapper">
          <input type="checkbox" v-model="checked" />
          我已阅读并接受上述内容
        </label>
        <button class="primary-btn" :disabled="!checked" @click="nextStep">下一步</button>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';

const checked = ref(false);
const router = useRouter();

function nextStep() {
  if (checked.value) {
    // 跳转到注册表单的下一页，请根据实际路由名称或路径替换
    router.push({ name: 'RegisterForm' });
  }
}
</script>

<style scoped>
.register-notice-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 24px;
  background: #f5f5f9;
}

.card {
  background: #ffffff;
  border-radius: 20px;
  max-width: 960px;
  width: 100%;
  padding: 48px 64px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  overflow-y: auto;
}

.title {
  text-align: center;
  font-size: 24px;
  font-weight: 600;
  margin-bottom: 32px;
}

h3 {
  font-size: 18px;
  margin: 24px 0 12px;
}

.section-list {
  list-style: none;
  counter-reset: item;
  padding-left: 0;
}

.section-list > li {
  counter-increment: item;
  margin-bottom: 12px;
}

.section-list > li::before {
  content: counter(item) "、";
  font-weight: 600;
  margin-right: 4px;
}

.indent {
  text-indent: 2em;
  margin-top: 8px;
}

.sub-list {
  list-style: none;
  padding-left: 0;
  margin-top: 8px;
}

.sub-list > li {
  padding-left: 2em;
  position: relative;
  margin-bottom: 4px;
}

.sub-list > li::before {
  content: attr(data-marker);
}

.footer {
  margin-top: 32px;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  flex-wrap: wrap;
  gap: 12px;
}

.checkbox-wrapper {
  display: flex;
  align-items: center;
  font-size: 14px;
  user-select: none;
}

.checkbox-wrapper input {
  margin-right: 8px;
}

.primary-btn {
  background: #409eff;
  color: #fff;
  border: none;
  padding: 10px 32px;
  border-radius: 4px;
  font-size: 16px;
  cursor: pointer;
  transition: background 0.2s ease;
}

.primary-btn:disabled {
  background: #c0c4cc;
  cursor: not-allowed;
}
</style>