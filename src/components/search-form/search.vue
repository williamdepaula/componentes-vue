<template>
    <div class="div-search col-lg-6 col-md-6 col-sm-6 col-xs-6 offset-3 float-md-center">
        <div class="search-form">
            <input type="search" v-model="valorBuscado" v-on:keyup="enviarBusca">
            <i class="fa fa-search"></i>
        </div>
    </div>
</template>
<script>
export default {
    name: 'search',
    data() {
        return {
            valorBuscado: ''
        }
    },
    methods: {
        enviarBusca: function() {
            this.$emit('realizarBusca', this.valorBuscado)
        }
    }
}
</script>

<style scoped>
    .search-form {
        position: relative;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
        transition: all 1s;
        width: 50px;
        height: 50px;
        background: white;
        box-sizing: border-box;
        border-radius: 25px;
        border: 4px solid white;
        padding: 5px;
    }

    input{
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;;
        height: 42.5px;
        line-height: 30px;
        outline: 0;
        border: 0;
        display: none;
        font-size: 1em;
        border-radius: 20px;
        padding: 0 20px;
    }

    .fa{
        box-sizing: border-box;
        padding: 10px;
        width: 42.5px;
        height: 42.5px;
        position: absolute;
        top: 0;
        right: 0;
        border-radius: 50%;
        color: #6c757d;
        text-align: center;
        font-size: 1.2em;
        transition: all 1s;
        border: 1px solid #6c757d;
    }

    .search-form:hover{
        width: 100%;
        cursor: pointer;
    }

    .search-form:hover input{
        display: block;
        border: solid 1px #6c757d;
    }

    .search-form:hover .fa{
        border: none;
    }

</style>