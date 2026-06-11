<template>
    <div>
        {{ user }}
        <input type="text" v-model="user.name">
        <input type="text" v-model="user.email">
        <UButton @click="adduser">add</UButton>
    </div>
</template>
<script setup>
const user = ref({
    name:'',
    email:""
})
const adduser = ()=>{
    $fetch('/api/users',{
        method:'POST',
        body:user.value
    })
}
</script>