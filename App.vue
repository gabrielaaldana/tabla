<template>
    <div>
 
<table border="1" align="center"  bordercolor="black" cellspacing="0">
    <th width="200" height="30" bgcolor="48A5E6">
        IdEmpleado
        </th>
        <th width="200" height="30" bgcolor="48A5E6" >
        nombre
        </th>
         <th width="200" height="30" bgcolor="48A5E6">
        apellido
        </th>
         <th width="200" height="30" bgcolor="48A5E6">
        dpi
        </th>
         <th width="200" height="30" bgcolor="48A5E6">
        email
        </th>
        


        
    <tr v-for="todo in todos" :key="todo.idEmpleado">
        
        <td bgcolor="D8EFFF" > {{todo.idEmpleado}}
        </td>

       
         <td bgcolor="91D6F1">{{todo.nombre}}
        </td>
        <td bgcolor="D8EFFF">{{todo.apellido}}
        </td>
        <td bgcolor="91D6F1">{{todo.dpi}}
        </td>
        <td bgcolor="D8EFFF">{{todo.email}}
        </td>
    </tr>
    
       
    
    
    
    


 </table>
     </div>
</template>

<script>
import axios from 'axios'
export default {
    data(){
        return{
            todos:null
        }
    }, 
    mounted (){
        this.getTodos();

    }   ,
    methods:{
        getTodos(){
            axios 
            .get('http://localhost:3000/prueba',{
                //username: 'admin',
                //password: 'admin'
            })
            .then(response => {
                console.log(response)
                this.todos=response.data

            })
            .catch(e=> console.log(e))
        }
    } 
}

</script>
<style>
</style>