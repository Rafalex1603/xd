<script setup lang="ts">
    import ListItem from './ListItem.vue';
    type Item = {
        title: string;
        isChecked: boolean;
    }
    const items: Item[] = [
        {
            title: "Leer un libro al mes",
            isChecked: false
        }
    ]
</script>

<template>
    <ul>
        <li :key="item.title" v-for="item in items">
            <ListItem :title="item.title" :isChecked="item.isChecked" />"
        



        </li>
    </ul>
</template>

<style scoped>
    
</style>