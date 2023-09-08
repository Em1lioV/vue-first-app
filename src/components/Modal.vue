<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ sale: theme === 'sale'}">

            <slot>defalut content</slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        props:['header','text','theme'],
        methods: {
            closeModal(){
                this.$emit('close')
            }
        },
    }
</script>
<!-- 
{scoped} tag hace que los estilos solo funcionen en este componenete - no se recomienda
hacerlo mucho porque puede agregar carga extra 
<style scoped>
    estilos solo para el componente
<style>
-->
<style> 
    .modal{
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius:10px ;
    }
    .backdrop{
        top: 0;
        position: fixed;
        background: rgba(0,0,0,0.5);
        width: 100%;
        height: 100%;
    }
    .modal h1{
        color: #03cfb4;
        border: none;
        padding: 0;

    }
    .modal .actions{
        text-align: center;
        margin: 30px 0 10px 0;
    }
    .modal .actions a{
        padding: 5px 10px;
        text-decoration: none;
        margin: 0 15px ;
        color: #2c3e50;
    }
    .modal.sale{
        background: crimson;
        color: white;

    }
    .modal.sale h1{
        color: white;
        
    }

    .modal.sale .actions a{
        border: 1px solid #ddd;
        color: antiquewhite;

     
    }
</style>