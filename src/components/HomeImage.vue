<template>
    <h1>Select a City</h1>
    <div class="container">
        <div @click="handleClickRight">
            <img class="image-right" 
            :src ="imageRight">
            
            <h4>{{cityRight}}</h4>
        </div>
        <div @click="handleClickCenter">
            <img class="image-center" 
            :src ="imageCenter">
            <h4>{{cityCenter}}</h4>
        </div>
        <div @click="handleClickLeft">
            <img class="image-left" 
            :src="imageLeft">
            <h4>{{cityLeft}}</h4>
        </div>
    </div>
    <h3>{{cityCenter}}</h3>

</template>

<script>
export default {
    data () {
        return {
            cityRight: 'Arequipa',
            cityCenter: 'Ica',
            cityLeft: 'Lima',
            imageRight:require('@/assets/city/AQP.jpg'),
            imageCenter:require('@/assets/city/ICA.jpg'),
            imageLeft:require('@/assets/city/LIM.jpg')
        }
    },
    methods:{
        handleClickRight() {
            this.imageRightOld=this.imageRight
            this.imageRight=this.imageCenter
            this.imageCenter=this.imageRightOld
            this.cityRightOld = this.cityRight
            this.cityRight = this.cityCenter
            this.cityCenter = this.cityRightOld
        },
        handleClickCenter() {
            this.cityCenter
        },
        handleClickLeft() {
            this.city = 'Lima'
            this.imageCenterOld=this.imageCenter
            this.imageCenter=this.imageLeft
            this.imageLeft=this.imageCenterOld
            this.cityCenterOld = this.cityCenter
            this.cityCenter = this.cityLeft
            this.cityLeft = this.cityCenterOld
        }
    }

}
</script>

<style>
.container {
    display: flex;
    justify-content: center;

}
.image-right {
    margin: 0 10px;
    width: 400px;
    height: 400px;
    object-fit: none;
}
.image-center{
    margin: 0 8px;
    width: 700px;
    height: 400px;
}
.image-left {
    margin: 0 10px;
    width: 400px;
    height: 400px;
    object-fit: none;
}
</style>