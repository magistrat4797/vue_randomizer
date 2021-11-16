<template>

    <section class="tasks-sec">
        <div class="wrapper">
            <div class="row">
                <div class="items-col col">
                    <input type="text" placeholder="Edit selected item" :value="activeItemValue" @input="setActiveItemValue" />
                    <ul class="items-list" v-for="(row, rowIndex) in fakeFetchData()" :key="rowIndex">
                        <Item v-for="item in row" :key="item.id" :title="item.title" :isActive="activeIndex === item.id" @click="onItemClick(item.id)" />
                    </ul>
                </div>
                <div class="actions-col col">
                    <button class="btn btn-default" v-on:click="shuffleItems">Shuffle Items</button>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

import Item from '@/components/Item.vue'

export default {
    name: 'ItemsList',
    data() {
        return {
            items: [
                { title: 'item 1' },
                { title: 'item 2' },
                { title: 'item 3' },
                { title: 'item 4' },
                { title: 'item 5' },
                { title: 'item 6' },
            ],
            activeIndex: -1,
            rowArray: [],
        }
    },
    components: {
        Item
    },
    computed: {
        activeItemValue() {
            return this.items[this.activeIndex]?.title ?? '';
        },
    },
    methods: {
        fakeFetchData(){
            var cloned = this.items.map((item, index) => { 
                return {title: item.title, id: index}
            });
            this.rowArray = [];
            while (cloned.length > 0) {
                let chunk = cloned.splice(0,3);
                this.rowArray.push(chunk);
            }  
            return this.rowArray;
        },
        shuffleItems() {
            let items = this.items,
                itemsCount = items.length,
                firstItem,
                secondItem,
                temp;
            for (let i = 0; i < itemsCount; i++) {
                firstItem = Math.floor(Math.random() * itemsCount);
                secondItem = Math.floor(Math.random() * itemsCount);
                temp = items[firstItem];
                items[firstItem] = items[secondItem];
                items[secondItem] = temp;
            }
            this.items = items;
        },
        onItemClick(index) {
            this.activeIndex = this.activeIndex === index ? -1 : index;
        },
        setActiveItemValue(event) {
            const foundItem = this.items[this.activeIndex];
            if (!foundItem) return;
            
            return this.items[this.activeIndex].title = event.currentTarget.value;
        },
    }
}
</script>
