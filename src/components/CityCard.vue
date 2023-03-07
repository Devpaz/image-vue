<template>
    <div>
        <img class="image-right" 
        :src="image">
        <h4>{{city}}</h4>
    </div>
</template>

<script>
export default {
    props: ['city','image']
}
</script>

<style>

</style>