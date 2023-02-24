<template>
    <div class="card mb-2">   
        <div class="card-body">
            <h5 class="text-center">{{ pais.name.common }}</h5>

            <p class="text-center">
                <img :src="pais.flags[0]" :alt="`bandera-${pais.name}`" class="img-fluid w-50">
            </p>
            <p class="card-text">
                <span class="badge text-bg-success p-2 d-block mb-1">Nombre Oficial: {{  pais.name.official }}</span>
                <span class="badge text-bg-dark d-block mb-1">Capital: {{ pais.capital[0]}}</span>
                <span class="badge text-bg-info p-3 d-block mb-1">Poblacion: {{numeroFormato( pais.population)}}</span>
                <span class="badge text-bg-dark d-block mb-1">Continente: {{ pais.region}}</span>
            </p>
        </div>
    </div>

</template>

<script>

export default { 
    props: ['pais'],

    setup(){
        const numeroFormato = (num) => {
            return new Intl.NumberFormat('en-US').format(num)


        }
        return {numeroFormato}
    }
}

</script>