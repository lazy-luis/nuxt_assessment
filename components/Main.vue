<template>
    <div class="container">
        <Filters :color-filters="colorFilters" :shape-filters="shapeFilters" :activeShapeFilters="activeShapeFilters" :activeColorFilters="activeColorFilters" />
        <h3> All Items </h3>
        <div class="items">
            <!-- Loop through shape filter and color filter-->
            <Item v-for="item in filteredItems" :key="item.id" :item="item" />
            </div>
    </div>
</template>
<script>
import Filters from './Filters.vue';
import Item from './Item.vue';
export default {
    name: 'Main',
    components: {
        Filters,
        Item
    },
    props: {
        shapeFilters: {
            type: Array,
            default: () => ['Oval', 'Round', 'Triangle', 'Square', 'Rectangle']
        },
        colorFilters: {
            type: Array,
            default: () => ['Red', 'Green', 'Blue']
        },
        activeShapeFilters: {
            type: Array,
            default: () => ['']
        },
        activeColorFilters: {
            type: Array,
            default: () => ['']
        },
        items: {
            type: Array,
            default: () => [
                {
                    id: 1,
                    shape: 'Oval',
                    color: 'Red'
                },
                {
                    id: 2,
                    shape: 'Round',
                    color: 'Green'
                },
                {
                    id: 3,
                    shape: 'Triangle',
                    color: 'Blue'
                },
                {
                    id: 4,
                    shape: 'Square',
                    color: 'Red'
                },
                {
                    id: 5,
                    shape: 'Rectangle',
                    color: 'Green'
                },
                {
                    id: 6,
                    shape: 'Oval',
                    color: 'Blue'
                },
                {
                    id: 7,
                    shape: 'Round',
                    color: 'Red'
                },
                {
                    id: 8,
                    shape: 'Triangle',
                    color: 'Green'
                },
                {
                    id: 9,
                    shape: 'Square',
                    color: 'Blue'
                },
                {
                    id: 10,
                    shape: 'Rectangle',
                    color: 'Red'
                },
                {
                    id: 11,
                    shape: 'Oval',
                    color: 'Green'
                },
                {
                    id: 12,
                    shape: 'Round',
                    color: 'Blue'
                },
                {
                    id: 13,
                    shape: 'Triangle',
                    color: 'Red'
                }
            ]
        }
    }
}
</script>
<style>
.container{
    display: flex;
    flex-direction: column;
    width: 60%;
    margin: 0 auto;
    padding: 30px 5%;
}
h3{
    font-size: 24px;
    font-weight: 900;
    margin-bottom: 30px;
}

@media (max-width: 768px) {
    .container{
        width: 90%;
    }
}
</style>