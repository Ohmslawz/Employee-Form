<template>
    <li>
       <img src="https://www.iconpacks.net/icons/2/free-user-icon-3297-thumb.png" alt="user"> 
       <hr/>
       <slot name="cardHeader"></slot>
       <slot name="cardButton"></slot>
       <slot name="cardContent"></slot>
    </li>
</template>

<script>
export default {
    name: "cardData",
}
</script>

<style scoped>
    li{
        margin:1rem 0;
        font-size: 1.25rem;
        font-weight: bold;
        background: purple;
        padding: 0.5rem;
        color: white;
        border-radius: 25px;
    }
    img{
        width: 75px;
        height: 75px;
    }
</style>