<template>
    <div class="card" id="marg">
        <div class="col-lg-12">
            <div class="col-lg-6">
                <input type="text" placeholder="type here" v-model="nombre">
                <input type="number" placeholder="type here" v-model="edad">
                <br>
                <button class="btn btn-success" @click="agregatePerson">+</button>
            </div>
            <div class="row col-lg-12">
                <ul v-for="el in datos" :key="el.pk">
                    <li>{{ el.name }} - {{ el.edad }}</li>
                </ul>
            </div>
        </div>
    </div>
</template>


<script>

export default {
    name: "ComponentFather",
    props: {
        data: {
            type: Object,
            required: true
        }
    },
    data: function () {
        return {
            datos: [],
            nombre: '',
            edad: 0
        }
    },
    methods: {
        agregatePerson() {
            let json = {
                name: this.nombre,
                pk: 0
            }
            this.datos.push(json);


        },
    }
};

</script>


<style>
#marg {
    margin: 100px !important;
}

input {
    margin: 5px;
}
</style>