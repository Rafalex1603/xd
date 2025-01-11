<script setup lang="ts">
    import { ref } from 'vue';
    import type { Ref } from 'vue';
    import ListItem from './ListItem.vue';
    type Item = {
        title: string;
        isChecked: boolean;
    }
    const items: Ref<Item[]> = ref([
        {
            title: "Leer un libro al mes",
            isChecked: false
        }
    ]);

    const updateItem = (element: Item): void => {
        const updatedItem = findItemList(element)
        if (updatedItem) {
            toggleItemCheck(updatedItem)
        }
    }
    const findItemList = (element: Item): Item | undefined => {
        return items.value.find((item: Item) => item.title === element.title)
    }
    const toggleItemCheck = (element: Item): void => {
        element.isChecked = !element.isChecked
    }
</script>



<template>
    <ul>
        <li :key="item.title" v-for="item in items">
            <ListItem :title="item.title" :isChecked="item.isChecked" @updateItem ="() => updateItem(item)" />"
                {{ item.title }}
            
        



        </li>
    </ul>
</template>

<style scoped>
    
</style>