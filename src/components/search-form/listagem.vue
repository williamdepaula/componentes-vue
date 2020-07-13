<template>
    <div>
        <search v-on:realizarBusca="busca"/>
        <div class="div-search col-lg-6 col-md-6 col-sm-6 col-xs-6 offset-3 float-md-center">
            <h4>Lista de Cidades</h4>
            <ul>
                <li v-for="cidade in listaCidadesFiltrada" :key="cidade">
                    {{cidade}}
                </li>
            </ul>

        </div>
    </div>    
</template>
<script>
import search from './search.vue'
export default {
    components: {
        search
    },
    created: function(){
        this.listaCidadesFiltrada = this.listaCidades
    },
    data() {
        return {
            listaCidades: [
                'Coxim',
                'Campo Grande',
                'Rio Verde',
                'Dourados',
                'Três Lagoas',
                'Corumbá',
                'Ponta Porã',
                'Sidrolândia',
                'Naviraí',
                'Nova Andradina',
                'Aquidauana',
                'Maracaju'
            ],
            listaCidadesFiltrada: []
        }
    },
    methods: {
      busca: function(valorBuscado) {
            this.listaCidadesFiltrada = this.listaCidades.filter( cidade => {
                return cidade.toLowerCase().includes(valorBuscado.toLowerCase())
            })  
      }  
    },
}
</script>