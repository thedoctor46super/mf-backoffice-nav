<template>
  <nav>
    <router-link to="/mf-backoffice-root/">Home</router-link>
    <router-link to="/mf-backoffice-root/about">About</router-link>
    <br /><br />
    <button @click="logout">Logout</button>
  </nav>
</template>

<script>
import cookie from 'js-cookie';
//import { useRouter } from 'vue-router';
import { onBeforeMount } from 'vue';

export default {
  name: 'SideNav',
  setup() {
    const router = VueRouter.useRouter();

    onBeforeMount(() => {
      if (!cookie.get('ft-portaltoken')) {
        router.push({ path: '/mf-backoffice-root/login' });
      }
    });

    const logout = () => {
      cookie.remove('ft-portaltoken', { path: '/', domain: document.domain });
      router.push({ path: '/mf-backoffice-root/login' });
    };

    return {
      logout,
    };
  },
};
</script>

<style scoped lang="less">
nav {
  position: fixed;
  background: rgb(62, 62, 231);
  padding: 20px 10px;
  left: 0;
  top: 0;
  bottom: 0;
  display: flex;
  flex-direction: column;

  * {
    color: #fff;
  }

  button {
    font-family: inherit;
    font-size: inherit;
    border: 0;
    background: none;
    text-decoration: underline;
    cursor: pointer;
  }
}
</style>
