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

    <el-main class="wrap">
        <div class="kalibry-card-wrap" v-for="item in books" :key="item.value" :label="item.label" :value="item.value">
            <div class="shoot">
                <img :src="item.value" class="image">
                <div class="shoot-option">
                    <el-avatar class="nano" size="small" src="https://cube.elemecdn.com/3/7c/3ea6beec64369c2642b92c6726f1epng.png"></el-avatar>
                    <div class="shoot-suboption">
                        <div class="text">
                            <p class="sub-title">{{item.label}}</p>
                        </div>
                        <div class="btn-box">
                            <el-popover placement="right" width="400" trigger="click">
                                <p> Este libro ... </p>
                                <el-button size="mini" slot="reference">Resumen</el-button>
                            </el-popover>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </el-main>
</div>
</template>

<style scoped>
.home {
    width: 100%;
    height: auto;
}

.btn-box {
    position: absolute;
    left: 68%;
    width: auto;
    top: 8px;
}

.shoot-suboption {
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
}

.sub-title {
    font-weight: 500;
    font-size: 13px;
    line-height: 1.3em;
    color: #333;
    margin: 0px 0 2px 0;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    max-width: 100%;
    position: relative;
    top: 5px;
}

.nano {
    width: 20px;
    height: 20px;
    margin-right: 10px;
    position: relative;
    top: 2px;
}

.kalibry-card-wrap {
    position: relative;
    clear: left;
    background: #fff;
    border-radius: 2px;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.07);
    overflow: hidden;
    width: 300px;
    height: 420px;
    margin: 10px;
}

.image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    background-position: center;
    cursor: pointer;
}

.shoot {
    padding: 10px;
    transition: padding 0.2s ease;
}

.shoot-option {
    box-sizing: border-box;
    display: flex;
    width: 100%;
    position: absolute;
    left: 0;
    bottom: 0;
    padding: 10px 10px 10px 10px;
    background: #fff;
    z-index: 2;
    will-change: transition;
    transition: height 0.2s ease;
}

.wrap {
    background-color: #f4f4f4;
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
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
            value: 'Reciente',
            books: [{
                    value: "https://damonza.com/wp-content/uploads/portfolio/nonfiction/Love6.jpg",
                    label: "Search for love"
                },
                {
                    value: "https://damonza.com/wp-content/uploads/portfolio/nonfiction/Set%20For%20Life%202.jpg",
                    label: "Set for life"
                },
                {
                    value: "https://damonza.com/wp-content/uploads/portfolio/nonfiction/Journey%20of%20an%20Introvert%206.jpg",
                    label: "Journy of an introvert"
                },
                {
                    value: "https://damonza.com/wp-content/uploads/portfolio/nonfiction/amsterdam-exposed_05_A.jpg",
                    label: "Amsterdam exposed"
                },
                {
                    value: "https://damonza.com/wp-content/uploads/portfolio/nonfiction/voice1b.jpg",
                    label: "Finding your voice"
                },
                {
                    value: "https://damonza.com/wp-content/uploads/portfolio/nonfiction/whatnerve1.jpg",
                    label: "What never"
                },
                {
                    value: "https://damonza.com/wp-content/uploads/portfolio/nonfiction/Some-Are-Sicker-Than-OthersD5.jpg",
                    label: "Some of them"
                },
                {
                    value: "https://damonza.com/wp-content/uploads/portfolio/nonfiction/RTFM1b.jpg",
                    label: "RTFM"
                },

            ]
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
