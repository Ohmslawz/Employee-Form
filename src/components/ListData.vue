<template>
        <ul>
            <!-- <ListPerson 
            v-for="item in employee"
            :id="item.id"
            :key="item.id"
            :nickName="item.nickName"
            :salary="item.salary"
            :department="item.department"
            :isVisible="item.isVisible"
            @show="toggleVisible"
            @delete="removeEmployee"
            /> -->
            <ListPerson 
            v-for="(item,index) in employee"
            :key="index"
            :nickName="item.nickName"
            :salary="item.salary"
            :department="item.department"
            :gender="item.gender"
            :skill="item.skill"
            />
        </ul>
</template>

<script>
import ListPerson from './ListPerson.vue'
export default {
    name: "ListData",
    components:{
        ListPerson
    },
    // data()
    //     return{
    //         employee: [
    //             {id:1, nickName:"Ohm", salary:30000, department:"Programer",isVisible:false},
    //             {id:2, nickName:"Boat", salary:40000, department:"Marketing",isVisible:false},
    //             {id:3, nickName:"Bam", salary:50000, department:"Sale",isVisible:false},
    //             {id:4, nickName:"Tey", salary:70000, department:"Accountant",isVisible:false},
    //             {id:5, nickName:"Luck", salary:30000, department:"Human Resource",isVisible:false}
    //         ]
    //     }
    // },
    // methods:{
    //     toggleVisible(id){
    //         this.employee = this.employee.map((item)=>{
    //             if(item.id === id){
    //                 return {...item,isVisible:!item.isVisible}
    //             }
    //             return item
    //         })
    //     },
    //     removeEmployee(id){
    //         this.employee = this.employee.filter(item=>{
    //             return item.id !== id
    //         })
    //     }
    // }
    props:["employee"]
};
</script>

<style scoped>
    ul{
        list-style: none;
        margin: 1rem;
        padding: 0;
    }
</style>