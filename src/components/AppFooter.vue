<template>
  <div class="Copyright">
    <span>2022, Powered by <a href="">Vectolabs Technologies Sdn Bhd</a></span>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "AppFooter",
});
</script>

<style scoped>
.Copyright {
    display: flex;
    justify-content: flex-end;
    padding: 0 40px;
}

.Copyright span {
    color: #b4b4b3;
    font-size: 0.825rem;
    font-weight: 600;
}

.Copyright a {
    text-decoration-line: none;
    color: #9bcbfc;
}

@media screen and (max-width: 620px){
    .Copyright{
        margin-top: 20px;
    }
}
</style>