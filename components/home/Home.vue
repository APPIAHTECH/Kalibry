<template>
<div class="home">

    <el-menu mode="horizontal" background-color="#333" text-color="#fff" active-text-color="#ffd04b">

        <el-menu-item>
            <h3 class="kalibry">Kalibry</h3>
        </el-menu-item>
        <el-menu-item index="2">Libros</el-menu-item>
        <el-menu-item index="3">Lectores</el-menu-item>
        <el-menu-item index="4">Comunidad</el-menu-item>

        <el-autocomplete class="el-autocomplete-box" prefix-icon="el-icon-search" v-model="state" :fetch-suggestions="querySearchAsync" placeholder="Buscar ..." @select="handleSelect"></el-autocomplete>

        <el-button class="btn-orange left" size="small" type="primary">Crear Historia</el-button>
        <el-dropdown class="down left">
            <span class="el-dropdown-link">
                <el-avatar size="small" src="https://cube.elemecdn.com/3/7c/3ea6beec64369c2642b92c6726f1epng.png"></el-avatar>
            </span>
            <el-dropdown-menu slot="dropdown">
                <el-dropdown-item>Mi perfil</el-dropdown-item>
                <el-dropdown-item divided>Bandeja de entrada</el-dropdown-item>
                <el-dropdown-item>Notificación</el-dropdown-item>
                <el-dropdown-item>Biblioteca</el-dropdown-item>
                <el-dropdown-item>Invitar a amigos</el-dropdown-item>
                <el-dropdown-item divided>Ajuda</el-dropdown-item>
                <el-dropdown-item>Configuración</el-dropdown-item>
                <el-dropdown-item>Salir</el-dropdown-item>

            </el-dropdown-menu>
        </el-dropdown>

    </el-menu>
    <el-menu mode="horizontal">
        <el-menu-item>
            <el-select v-model="value" placeholder="Select">
                <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value">
                </el-option>
            </el-select>
        </el-menu-item>

        <el-menu-item index="5">Todos</el-menu-item>
        <el-menu-item index="6">Acción</el-menu-item>
        <el-menu-item index="7">Aventura</el-menu-item>
        <el-menu-item index="8">Ciencia Ficción</el-menu-item>
        <el-menu-item index="9">Romance</el-menu-item>
        <el-menu-item index="10">Terror</el-menu-item>
        <el-menu-item index="11">Poesía</el-menu-item>
        <el-menu-item index="12">Vampiros</el-menu-item>
        <el-menu-item index="13">Misterio</el-menu-item>
        <el-submenu index="14">
            <template slot="title">Más</template>
            <el-menu-item index="14-1">Novela juvenil</el-menu-item>
            <el-menu-item index="14-2">Suspenso</el-menu-item>
            <el-menu-item index="14-3">Espiritual</el-menu-item>
        </el-submenu>
    </el-menu>
</div>
</template>

<style scoped>
.home {
    width: 100%;
    height: auto;
}

.kalibry {
    color: #AED581;
    font-weight: normal;
}

.el-autocomplete-box {
    top: 6px;
    width: 40%;
}

.el-avatar {
    outline: none;
    cursor: pointer;
}

.down,
.btn-orange {
    position: relative;
    top: 16px;
}

.left {
    position: relative;
    left: 15%;
}

.btn-orange {
    top: 6px;
    margin-right: 10px;
    border: none;
    background-color: #f44336;
}

.btn-orange:hover {
    background-color: #ff5252;
}
</style>

<script>
export default {
    data() {
        return {
            links: [],
            state: '',
            timeout: null,
            options: [{
                value: 'popular',
                label: 'Popular'
            }, {
                value: 'reciente',
                label: 'Reciente'
            }, {
                value: 'antiguo',
                label: 'Antiguo'
            }],
            value: 'Reciente'
        };
    },
    methods: {
        loadAll() {
            return [{
                    "value": "vue",
                    "link": "https://github.com/vuejs/vue"
                },
                {
                    "value": "element",
                    "link": "https://github.com/ElemeFE/element"
                },
                {
                    "value": "cooking",
                    "link": "https://github.com/ElemeFE/cooking"
                },
                {
                    "value": "mint-ui",
                    "link": "https://github.com/ElemeFE/mint-ui"
                },
                {
                    "value": "vuex",
                    "link": "https://github.com/vuejs/vuex"
                },
                {
                    "value": "vue-router",
                    "link": "https://github.com/vuejs/vue-router"
                },
                {
                    "value": "babel",
                    "link": "https://github.com/babel/babel"
                }
            ];
        },
        querySearchAsync(queryString, cb) {
            var links = this.links;
            var results = queryString ? links.filter(this.createFilter(queryString)) : links;

            clearTimeout(this.timeout);
            this.timeout = setTimeout(() => {
                cb(results);
            }, 3000 * Math.random());
        },
        createFilter(queryString) {
            return (link) => {
                return (link.value.toLowerCase().indexOf(queryString.toLowerCase()) === 0);
            };
        },
        handleSelect(item) {
            console.log(item);
        }
    },
    mounted() {
        this.links = this.loadAll();
    }
};
</script>
