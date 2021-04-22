<template>
    <div class="parent">
        <div class="header"></div>
        <div class="conent"></div>
        <div class="footer"></div>
    </div>
</template>
<script>
// import { defineComponent } from '@vue/composition-api'

export default {
    data() {
        return {

        }
    }
}
</script>

<style scoped>
.parent{
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
}
.header{
    
    height: 100px;
    background: #f00;
}
.conent{
    flex: 1;
    overflow: hidden;
}

.footer{
    height: 100px;
    background: #f00;
}
</style>
