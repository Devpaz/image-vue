<template>
    <h1>Select a City</h1>
    <div class="container">
        <CityCard 
        :btn=handleClickRight
        :image =imageRight
        :city=cityRight
        />

        <CityCardSelected 
        :image=imageCenter
        :city=cityCenter
        />

        <CityCard 
        :btn=handleClickLeft
        :image =imageLeft
        :city=cityLeft
        />
    </div>
    <CityInfo
    :city=cityCenter
    />
</template>

<script>
import CityCard from '@/components/CityCard'
import CityCardSelected from '@/components/CityCardSelected'
import CityInfo from '@/components/CityInfo'


export default {
    components: {
    CityCard, CityCardSelected,CityInfo
    },
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
        handleClickLeft() {
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