
<script>
import AppHeader from "@/components/AppHeader.vue";
import { CKEditor } from "ckeditor4-vue";
export default {
    components: {
    AppHeader,
    CKEditor
},
};

</script>

<template>
    <div id="app">
        <AppHeader/>
     
        <div class="container mt-3">
            <router-view />
            <CKEditor></CKEditor>
        </div>
    </div>
</template>

<style>
    .page {
        max-width: 400px;
        margin: auto;
    }
    
</style>
