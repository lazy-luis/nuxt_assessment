<template>
    <div>
    <h3> Filters </h3>
        <div>
            <div class="filter">
                <p> Shape </p>
                <div class="filters">
                    <label v-for="shape in shapeFilters" :key="shape" class="" :class="{active: activeShapeFilters.includes(shape)}" v-on:click="toggleShapeFilter(shape)">
                        {{shape}}
                    </label>
                </div>
            </div>
            <div class="filter">
                <p> Color </p>
                <div class="filters">
                    <label v-for="color in colorFilters" :key="color" class="" :class="{active: activeColorFilters.includes(color)}" v-on:click="toggleColorFilter(color)">{{ color }}</label>
                </div>
            </div>
        </div></div>
</template>
<script>
export default {
    name: 'Filters',
    props: ['shapeFilters', 'colorFilters', 'activeShapeFilters','activeColorFilters'],
    methods: {
        toggleShapeFilter(shape) {
            if (this.activeShapeFilters.includes(shape)) {
                this.activeShapeFilters = this.activeShapeFilters.filter((item) => item !== shape);
            } else {
                this.activeShapeFilters.push(shape);
            }
        },
        toggleColorFilter(color) {
            if (this.activeColorFilters.includes(color)) {
                this.activeColorFilters = this.activeColorFilters.filter((item) => item !== color);
            } else {
                this.activeColorFilters.push(color);
            }
        }
    },
}
</script>
<style scoped>

h3{
    font-size: 24px;
    font-weight: 900;
    margin-bottom: 30px;
}
    .filter{
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: flex-start;
    gap: 20px;
    margin-bottom: 20px;
}
.filter p{
    font-size: 18px;
    font-weight: 500;
    color: blue;
}

.filter .filters {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    gap: 20px;
    flex-wrap: wrap;
}
.filter .filters label{
    font-size: 12px;
    font-weight: 500;
    color: #000000;
    padding: 10px 20px;
    border-radius: 20px;
    background-color: #f5f5f5;
    border: 1px solid #e5e5e5;
}

.filter .filters label:hover{
    background-color: #e5e5e5;
    border: 1px solid #d5d5d5;
}

.filter .filters label.active{
    background-color: #e5e5e5;
    border: 1px solid #d5d5d5;
}
</style>