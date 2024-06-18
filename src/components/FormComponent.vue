<template>
    <form @submit.prevent="submitForm">
        <div class="form-control">
            <label for="emp-name">Employee Name</label>
            <input type="text" v-model.trim="employee.nickName"/>
        </div>
        <div class="form-control">
            <label for="salary">Salary</label>
            <input type="number" v-model.trim="employee.salary"/>
        </div>
        <div class="form-control">
            <label for="gender">Gender</label>
            <div>
                <input type="radio" value="Male" v-model="employee.gender"/>
                <label for="gender-name">Male</label>
            </div>
            <div>
                <input type="radio" value="Female" v-model="employee.gender"/>
                <label for="gender-name">Female</label>
            </div>
        </div>
        <div class="form-control">
            <label for="skill">Language</label>
            <div>
                <input type="checkbox" value="English" v-model="employee.skill"/>
                <label for="skill">English</label>
            </div>
            <div>
                <input type="checkbox" value="Japanese" v-model="employee.skill"/>
                <label for="skill">Japanese</label>
            </div>
            <div>
                <input type="checkbox" value="Chinese" v-model="employee.skill"/>
                <label for="skill">Chinese</label>
            </div>
            <div>
                <input type="checkbox" value="Thai" v-model="employee.skill"/>
                <label for="skill">Thai</label>
            </div>
        </div>
        <div class="form-control">
            <label for="department">Position</label>
            <select v-model.trim="employee.department">
                <option value="Marketing">Marketing</option>
                <option value="Programer">Programer</option>
                <option value="Sale">Sale</option>
                <option value="Accountant">Accountant</option>
                <option value="Human Resource">Human Resource</option>
            </select>
        </div>
        <div class="button-control">
            <button>Submit
            </button>
        </div>
    </form>
</template>

<script>
export default {
    name: "FormComponent",
    data(){
        return{
            employee:{
                nickName:"",
                salary:0,
                department:"Marketing",
                gender:"",
                skill:[] //ใส่เป็น array เพื่อให้สามารถรับ input ได้หลายค่า
            }
        }
    },
    methods:{
        submitForm(){
            const newEmployee={
                nickName: this.employee.nickName,
                salary: this.employee.salary,
                department: this.employee.department,
                gender: this.employee.gender,
                skill: this.employee.skill
            }
            this.$emit("save",newEmployee);
            this.resetForm();
        },
        resetForm(){
            this.employee.nickName="";
            this.employee.salary="";
            this.employee.department="Marketing";
            this.employee.gender="";
            this.employee.skill=[];
        }
    }
}
</script>

<style scoped>
    form{
        box-shadow: 0 2px 8px rgba(0,0,0,0.25);
        margin: 3rem;
        border-radius: 10px;
        padding:  1rem;
    }
    .form-control{
        margin: 0.5rem;
    }
    label{
        font-weight: bold;
    }
    input,select{
        display: block;
        width: 100%;
        font: inherit;
        margin-top: 0.5 rem;
    }
    .button-control{
       text-align: center;
    }
    button{
        background-color: green;
        font: inherit;
        color:white;
        cursor: pointer;
        padding: 0.5rem;
        width: 100px;
    }
    input[type="radio"],input[type="checkbox"]{
        display:inline-block;
        width: auto;
        margin-right: 1rem;
    }
    input[type="radio"]+label,input[type="checkbox"]+label{
        font-weight: normal;
    }
</style>