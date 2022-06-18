<template>
    <div class="generator-wrapper">
        <div class="generator__content">
            <h3 class="generator__title">Random Gift Generator</h3>
            <div class="generator__form flex direction-column">
                <div class="generator__formGroup">
                    <label for="">Título</label>
                    <input type="text" v-model="titulo">
                </div>
                <div class="generator__formGroup">
                    <label for="">Filtro Imagen</label>
                    <select @change="getFilterVal">
                        <option value="0">Seleccione un filtro</option>
                        <option v-for="(filtro, index) in filtros" :key="index" :value="filtro.valor">{{ filtro.nombre }}
                        </option>
                    </select>
                </div>
                <div class="generator__formGroup">
                    <label for="">Color Título</label>
                    <select @change="getColorVal">
                        <option value="0">Seleccione un color</option>
                        <option v-for="(color, index) in colores" :key="index" :value="color.valor">{{ color.nombre }}
                        </option>
                    </select>
                </div>
                <div class="generator__formGroup">
                    <label for="">Tamaño Título</label>
                    <input type="text" v-model="tamano">
                </div>
                <div class="generator__formGroup">
                    <input type="submit" value="Obtener mi gatito" @click="getGifCat()">
                </div>
            </div>
        </div>
        <div class="generator__response">
            <img :src="gif">
        </div>
    </div>
</template>

<script>
export default {
    name: 'gif-cat',
    //props: {},
    data: function(){
        return {
            gif: '',
            titulo: '',
            tamano: '',
            filtros: [
                {
                    nombre: 'Blur',
                    valor: 'blur'
                },
                {
                    nombre: 'Mono',
                    valor: 'mono'
                },
                {
                    nombre: 'Sepia',
                    valor: 'sepia'
                },
                {
                    nombre: 'Negative',
                    valor: 'negative'
                },
                {
                    nombre: 'Paint',
                    valor: 'paint'
                },
                {
                    nombre: 'Pixel',
                    valor: 'pixel'
                }
            ],
            filtro: '',
            colores: [
                {
                    nombre: 'Rojo',
                    valor: 'red'
                },
                {
                    nombre: 'Azul',
                    valor: 'blue'
                },
                {
                    nombre: 'Verde',
                    valor: 'green'
                },
                {
                    nombre: 'Blanco',
                    valor: 'white'
                },
                {
                    nombre: 'Amarillo',
                    valor: 'yellow'
                }
            ],
            color: ''
        }
    },
    // computed: {},
    methods: {
        getFilterVal(e) {
            this.filtro = e.target.value
        },
        getColorVal(e) {
            this.color = e.target.value
        },
        getGifCat() {
            let catGif = ''
            if(this.filtro == 'pixel') {
                catGif = `https://cataas.com/cat/says/${this.titulo}?filter=${this.filtro}&color=${this.color}&size=${this.tamano}&type=or`
            } else {
                catGif = `https://cataas.com/cat/gif/says/${this.titulo}?filter=${this.filtro}&color=${this.color}&size=${this.tamano}&type=or`
            }
            this.gif = catGif
        }
    },
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}
</script>

<style scoped>
/* Generator */
.generator-wrapper {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    width: 100%;
}

.generator__content {
    background-color: #021E66;
    padding: 3.125rem;
}

.generator__title {
    font-size: 1.5rem;
    margin-bottom: 1.875rem;
}


.generator__formGroup {
    display: flex;
    flex-direction: column;
    gap: .625rem;
}

.generator__formGroup input,
.generator__formGroup select {
    border: none;
    padding: .625rem;
}

.generator__formGroup input:hover,
.generator__formGroup input:focus,
.generator__formGroup select:hover,
.generator__formGroup select:focus {
    outline: none;
}

.generator__formGroup input[type="submit"] {
    align-self: center;
    background-color: hsl(var(--primary-color));
    color: hsl(var(--secondary-color));
    cursor: pointer;
    margin-top: 1.25rem;
    padding: .625rem;
    text-transform: uppercase;
    transition: background 650ms ease-in-out;
}
.generator__formGroup input[type="submit"]:hover,
.generator__formGroup input[type="submit"]:focus {
    background-color: hsl(var(--primary-color-tint))
}

.generator__response {
    background-image: url(../assets/bg-result.jpg);
    background-position: center;
    background-size: cover;
    display: grid;
    place-items: center;
}
</style>