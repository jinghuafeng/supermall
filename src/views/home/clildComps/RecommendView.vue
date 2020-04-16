<template>
    <div class="recommend">
        <div v-for="item in recommend" :key="item.image" class="recommend-item">
            <a :href="item.link" class="link">
                <img :src="item.image" alt="" class="image">
                <span>{{item.title}}</span>
            </a>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        recommend:{
            type:Array,
             default(){
                return []
            }
        }
    }
}
</script>
<style scoped>

.recommend{
    display: flex;
    width: 100%;
    text-align: center;
    padding: 10px 0 20px;
    border-bottom:8px solid #eee;
}
.image{
    width: 70px;
    height: 70px;
    margin-bottom: 10px;
}
.recommend-item{
    flex: 1;
}


</style>