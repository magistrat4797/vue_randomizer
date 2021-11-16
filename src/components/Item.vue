<template>
    <li class="item">
        <div class="item-box" :class="{ active: isActive }">
            {{ title }}
        </div>
    </li>
</template>

<script>

export default {
    name: 'ItemsList',
    props: {
        title: String,
        isActive: Boolean
    }
}
</script>