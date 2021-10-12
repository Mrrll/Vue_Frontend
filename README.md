# vue-frondend
Aprendiendo Vue Js
<a name="top"></a>

## Índice de contenidos

- [Instalacion Vue Cli](#item1)
- [Instalacion Vuetify](#item2)
- [Comandos Ejecutables](#item3) 
- [Personalizar la configuración](#item4)
- [Comunicación Hijo a Padre (evento)](#item5)
- [Comunicación Padre a Hijo (evento)](#item6)

## Vu-Cli
<a name="item1"></a>
### Instalacion
>`Typee:` En Consola ...
```console
npm install -g @vue/cli
```
>Crear nuevo Proyecto
```console
vue create hello-world
```
O Usando GUI
```console
vue ui
```
[Subir](#top)
<a name="item2"></a>
### Instalacion Vuetify
>`Typee:` En Consola ...
```console
vue add vuetify
```
## Project setup
```
npm install
```
[Subir](#top)
<a name="item3"></a>

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```
[Subir](#top)
<a name="item4"></a>

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

[Subir](#top)
<a name="item5"></a>
### Comunicación Hijo a Padre (evento)

**`Nota:` 
Para crear el nombre de referencia del componente hijo se utiliza `$ref` segido del (Nombre) `$ref='nombre'` en este caso el nombre es `componente`.**

> Archivo Padre y dentro de el :

```vue
<hijo ref="componente"></hijo>
<v-btn @click="PruebaPadre">Prueba</v-btn>

<script>
export default {
    methods: {
        PruebaPadre(){
            this.$refs.componente.PruebaHijo()
        }
    },
}
</script>
```
> Archivo Hijo y dentro de el :

```vue
<script>
export default {  
    methods: {   
        PruebaHijo(){
            console.log("HOLA DESDE PRUEBA HIJO");
        }
    },
}
</script>
```
[Subir](#top)

<a name="item6"></a>
### Comunicación Padre a Hijo (evento)

**`Nota:` 
Para emitir un metodo se utiliza  `@` y un nombre de referencia `@prueba` y indicamos el metodo del padre que queremos emitir `@prueba='PruebaPadre'`.**

> Archivo Padre y dentro de el :

```vue
<hijo @prueba="PruebaPadre"></hijo>
 
<script>
export default {
    methods: {
        PruebaPadre(){
            console.log("HOLA DESDE PRUEBA PADRE");
        }
    },
}
</script>
```
> Archivo Hijo y dentro de el :

```vue
<v-btn @click="PruebaHijo">Prueba</v-btn>

<script>
export default {  
    methods: {   
        PruebaHijo(){
            this.$emit("prueba");
        }
    },
}
</script>
```
[Subir](#top)
