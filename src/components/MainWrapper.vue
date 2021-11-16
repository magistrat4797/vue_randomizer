<template>
    <section class="page-wrap">
        <Tasks/>
        <div class="col">
            <ItemsList/>
        </div>
    </section>
</template>

<script>

import Tasks from '@/components/Tasks.vue'
import ItemsList from '@/components/ItemsList.vue'

export default {
    name: 'MainWrapper',
    components: {
        Tasks,
        ItemsList
    }
}
</script>
