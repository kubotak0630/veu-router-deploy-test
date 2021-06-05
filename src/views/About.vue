<template>
  <div class="about">
    <h1>This is an about page</h1>
    <el-button class="btn" type="primary" @click="handleGoBackHome">GoBack Home Page</el-button>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import { useRouter } from "vue-router";

export default defineComponent({
  name: "About",
  setup() {
    const router = useRouter();

    const handleGoBackHome = () => {
      router.push({ name: "Home" });
    };

    return { handleGoBackHome };
  },
});
</script>
