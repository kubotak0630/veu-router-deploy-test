<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <el-button class="btn" type="primary" @click="handleClick">Primary</el-button>

    {{ cnt }}
    <div>
      <el-button class="btn" type="primary" @click="handleGoAboutPage">Go About Page</el-button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import { useRouter } from "vue-router";

export default defineComponent({
  name: "HelloWorld",
  props: {
    msg: String,
  },
  setup() {
    const router = useRouter();
    const cnt = ref(0);

    const handleClick = () => {
      cnt.value++;
    };

    const handleGoAboutPage = () => {
      router.push({ name: "About" });
    };

    return { cnt, handleClick, handleGoAboutPage };
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.btn {
  margin-bottom: 10px;
}

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
