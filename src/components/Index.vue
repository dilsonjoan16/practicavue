<template lang="html">
  <div class="container">
    <div id="tareas" class="shadow-lg bg-grey-800 rounded col-sm-8 col-sm-offset-2 mx-auto my-auto">
        <form v-on:submit="agregartarea" class="mx-auto mt-2">
            <input type="text" v-model="tareas.titulo" placeholder="Nombre de la tarea" class="mb-2 form-control" required>
            <input type="text" v-model="tareas.descripcion" placeholder="Descripcion de la tarea" class="form-control" required> <br>
            <input type="submit" value="Agregar" class="btn btn-success btn-block mb-1">
        </form>
        <table class="table">
            <thead>
                <tr>
                    <th>
                        Realizado
                    </th>
                    <th>
                        Tarea
                    </th>
                    <th>
                        Descripcion
                    </th>
                    <th>
                        Eliminar
                    </th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="tarea in tareas" v-bind:key="tarea">
                    <td>
                        <input type="checkbox" v-model="tarea.hecho">
                    </td>
                    <td :class="{tarearealizada: tarea.hecho}">
                        {{tarea.titulo}}
                    </td>
                    <td :class="{tarearealizada: tarea.hecho}">
                        {{tarea.descripcion}}
                    </td>
                    <td>
                        <button v-on:click="eliminartarea(tarea)" class="btn btn-danger">
                            Eliminar
                        </button>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
  </div>
</template>
<script>
export default {

        data(){
            return{
            tareas: [
                
            ]
        }
    },
        methods: {
            agregartarea: function(e){
                e.preventDefault();
                alert("Tarea creada con exito!");
                this.tareas.push({
                    titulo: this.tareas.titulo,
                    descripcion: this.tareas.descripcion,
                    hecho: false
                });
                this.tareas.titulo = '';
                this.tareas.descripcion = '';
            },
            eliminartarea: function(tarea){
                this.tareas.splice(this.tareas.indexOf(tarea),1);
                alert("Tarea eliminada con exito!")
            }
        }
};
    
</script>
<style lang="css">
.tarearealizada{
    text-decoration: line-through;
    text-decoration-color: #3eae7c ;
}
#tareas{
    
}
</style>
