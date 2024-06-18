<template>
    <cardData>
        <template v-slot:cardHeader>
            <h1>{{ nickName }}</h1>
        </template>
        <!-- <template v-slot:cardButton>
            <button @click="showDescription(id)">Details</button> &puncsp;
            <button @click="deleteEmployee(id)">Delete</button>
        </template> -->
        <template v-slot:cardContent>
            <!-- <transition name="fade"> -->
            <!-- <div v-show="isVisible"> -->
            <p>
                Salary : {{ salary }} <br>
                Gender : {{ gender }} <br>
                Department : {{ department }} <br>
                Communication Language : {{ skill }}
            </p>
            <!-- </div>
            </transition> -->
        </template>
    </cardData>
</template>

<script>
import cardData from './cardData.vue'
export default {
    name: "ListPerson",
    components:{
        cardData
    },
    props:{
        id:{
            type: Number
        },
        nickName:{
            type: String,
            required:true
        },
        salary:{
            type:Number,
            required:true
        },
        department:{
            type:String,
            require:true
        },
        gender:{
            type:String,
        },
        skill:{
            type:Array
        }
    //     isVisible:{
    //         type:Boolean
    //     }
    // },
    // methods:{
    //     showDescription(id){
    //         this.$emit("show",id)
    //     },
    //     deleteEmployee(id){
    //         this.$emit("delete",id)
    //     }
    }
}
</script>

<style scoped>
    h1{
        color: yellowgreen;
    }
    button{
        font:inherit;
        cursor: pointer;
        border: 1px solid #ff0077;
        background: #ff0077;
        color:white;
        padding:0.05rem 1rem;
        box-shadow: 1px 1px 2px rgba(0,0,0,0.26);
        border-radius: 20px;
    }
    .fade-enter-from{
        opacity: 0;
    }
    .fade-enter-active{
        transition: all 0.5s linear;
    }
</style>