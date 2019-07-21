<template>
<el-container class="home">

    <el-container>
        <el-header>
            <el-menu class="el-menu-demo" mode="horizontal">
                <el-menu-item>Kalibry</el-menu-item>

                <el-menu-item id="search">

                    <el-autocomplete class="inline-input" v-model="state2" :fetch-suggestions="querySearch" placeholder="Buscar ..." prefix-icon="el-icon-search" :trigger-on-focus="false" @select="handleSelect"></el-autocomplete>

                </el-menu-item>
                <el-menu-item>
                    <el-button type="primary" size="mini"> Search</el-button>
                </el-menu-item>

                <el-menu-item>
                    <el-avatar size="small" src='https://cube.elemecdn.com/3/7c/3ea6beec64369c2642b92c6726f1epng.png' id="avatar"></el-avatar>
                    <el-dropdown trigger="click">
                        <span class="el-dropdown-link">
                            Stephen Appiah<i class="el-icon-arrow-down el-icon--right"></i>
                        </span>
                        <el-dropdown-menu slot="dropdown">
                            <el-dropdown-item icon="el-icon-plus">Action 1</el-dropdown-item>
                            <el-dropdown-item icon="el-icon-circle-plus">Action 2</el-dropdown-item>
                            <el-dropdown-item icon="el-icon-circle-plus-outline">Action 3</el-dropdown-item>
                            <el-dropdown-item icon="el-icon-check">Action 4</el-dropdown-item>
                            <el-dropdown-item icon="el-icon-circle-check-outline">Action 5</el-dropdown-item>
                        </el-dropdown-menu>
                    </el-dropdown>
                    <i class="el-icon-bell"></i>
                </el-menu-item>

            </el-menu>

        </el-header>

        <el-main>


            <!-- TENDENCIA -->
            <div class="secction">
                <h2>Tendenia</h2>
                <div class="book-list">
                    <div class="card-container">
                        <div class="top">
                            <img src="https://damonza.com/wp-content/uploads/portfolio/nonfiction/Rock%20Your%20Au%20Pair%20Year%201.8.jpg" class="image">
                        </div>
                        <div class="bot">
                            <div id="name">
                                <h3>Au Pair</h3>
                            </div>
                            <div id="stats">
                                <span class="stats-span">Stephen</span>
                            </div>
                        </div>
                    </div>

                    <div class="card-container">
                        <div class="top">
                            <img src="https://damonza.com/wp-content/uploads/portfolio/nonfiction/Writer11.jpg" class="image">
                        </div>
                        <div class="bot">
                            <div id="name">
                                <h3>Rescue</h3>
                            </div>
                            <div id="stats">
                                <span class="stats-span">Stephen</span>
                            </div>
                        </div>
                    </div>

                    <div class="card-container">
                        <div class="top">
                            <img src="https://damonza.com/wp-content/uploads/portfolio/nonfiction/Grit7.jpg" class="image">
                        </div>
                        <div class="bot">
                            <div id="name">
                                <h3>Grift</h3>
                            </div>
                            <div id="stats">
                                <span class="stats-span">Stephen</span>
                            </div>
                        </div>
                    </div>

                    <div class="card-container">
                        <div class="top">
                            <img src="https://damonza.com/wp-content/uploads/portfolio/nonfiction/2453_B.jpg" class="image">
                        </div>
                        <div class="bot">
                            <div id="name">
                                <h3>Bussines Plan</h3>
                            </div>
                            <div id="stats">
                                <span class="stats-span">Stephen</span>
                            </div>
                        </div>
                    </div>

                    <div class="card-container">
                        <div class="top">
                            <img src="https://damonza.com/wp-content/uploads/portfolio/nonfiction/Love6.jpg" class="image">
                        </div>
                        <div class="bot">
                            <div id="name">
                                <h3>Love</h3>
                            </div>
                            <div id="stats">
                                <span class="stats-span">Stephen</span>
                            </div>
                        </div>
                    </div>

                    <div class="card-container">
                        <div class="top">
                            <img src="https://images-na.ssl-images-amazon.com/images/I/51uLvJlKpNL._SX321_BO1,204,203,200_.jpg" class="image">
                        </div>
                        <div class="bot">
                            <div id="name">
                                <h3>The Hobbit</h3>
                            </div>
                            <div id="stats">
                                <span class="stats-span">Stephen</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- MAS VISTO-->
            <div class="secction">
                <h2>Más Visto</h2>
                <div class="book-list">
                    <div class="card-container-big">
                        <div class="top-big">
                            <img src="https://damonza.com/wp-content/uploads/portfolio/nonfiction/Vegan3.jpg" class="image">
                        </div>
                        <div class="bot-big">
                            <div id="name">
                                <h3>Vegan 3</h3>
                            </div>
                            <div id="stats">
                                <span class="stats-span">Stephen</span>
                            </div>
                        </div>
                    </div>

                    <div class="card-container-big">
                        <div class="top-big">
                            <img src="https://damonza.com/wp-content/uploads/portfolio/nonfiction/Improve-Your-Social-Skills_ebook.jpg" class="image">
                        </div>
                        <div class="bot-big">
                            <div id="name">
                                <h3>Improve Your Social Skills</h3>
                            </div>
                            <div id="stats">
                                <span class="stats-span">Stephen</span>
                            </div>
                        </div>
                    </div>

                    <div class="card-container-big">
                        <div class="top-big">
                            <img src="https://damonza.com/wp-content/uploads/portfolio/nonfiction/WifeandWar5.jpg" class="image">
                        </div>
                        <div class="bot-big">
                            <div id="name">
                                <h3>Wify and War 5</h3>
                            </div>
                            <div id="stats">
                                <span class="stats-span">Stephen</span>
                            </div>
                        </div>
                    </div>

                    <div class="card-container-big">
                        <div class="top-big">
                            <img src="https://damonza.com/wp-content/uploads/portfolio/nonfiction/onlinedating_frontHR.jpg" class="image">
                        </div>
                        <div class="bot-big">
                            <div id="name">
                                <h3>Online Dating</h3>
                            </div>
                            <div id="stats">
                                <span class="stats-span">Stephen</span>
                            </div>
                        </div>
                    </div>

                    <div class="card-container-big">
                        <div class="top-big">
                            <img src="https://damonza.com/wp-content/uploads/portfolio/nonfiction/Kellys-Kitchen-Savvy_ebook.jpg" class="image">
                        </div>
                        <div class="bot-big">
                            <div id="name">
                                <h3>Kitcher Savvy</h3>
                            </div>
                            <div id="stats">
                                <span class="stats-span">Stephen</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

        </el-main>

    </el-container>

</el-container>
</template>

<style>

.home{
    background-color: #FAFAFA;
}
.book-list {
    display: flex;
    flex-flow: row nowrap;
}

#search {
    width: 62%;
}

#name,
#stats {
    margin-left: 20px;
    text-align: justify;
}

#name {
    margin-top: 15px;
}

#name h3 {
    font-stretch: normal;
    font-weight: bold;
    opacity: .8;
    font-size: 12pt;
}

#stats {
    margin-bottom: 20px;
}

.stats-span {
    opacity: .6;
}

.card-container,
.card-container-big {
    width: 210px;
    height: 200px;
    box-sizing: border-box;
    border-radius: 8px;
    box-shadow: 10px 10px 5px -6px rgba(236, 240, 241, 1);
    margin-right: 10px;
    cursor: pointer;
}

.card-container-big {
    width: 300px;
    height: 300px;
}

.top,
.bot,
.bot-big,
.top-big {
    width: 100%;
    height: 60%;
    display: flex;
    background-color: white;
}

.bot,
.bot-big {
    height: 40%;
    flex-flow: column nowrap;
    justify-content: space-between;
    align-items: baseline;
}

.bot-big {
    height: 26%;
}

.top-big {
    height: 75%;
}

.secction {
    width: 100%;
    height: auto;
    box-sizing: border-box;
    margin-top: 5px;
    flex-flow: column nowrap;
    padding: 5%;
    padding-bottom: 0;

}

.secction h2 {
    opacity: .5;
    margin-bottom: 30px;
    letter-spacing: normal;
    text-align: justify;
    font-size: 130%;
}

.el-carousel__item h3 {
    color: #475669;
    font-size: 18px;
    opacity: 0.75;
    line-height: 300px;
    margin: 0;
}

.el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n+1) {
    background-color: #d3dce6;
}

#search .el-autocomplete {
    width: 100% !important;
}

.el-header {
    background-color: #B3C0D1;
    color: #333;
    line-height: 60px;
    padding: 0;
}

.el-aside {
    color: #333;
}

.el-dropdown-link {
    cursor: pointer;
}

.el-icon-arrow-down {
    font-size: 12px;
}

.demonstration {
    display: block;
    font-size: 14px;
    margin-bottom: 20px;
}

.el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
}

.image,
.slide-image {
    background-position: center;
    background-repeat: no-repeat;
    width: 100%;
    object-fit: cover;
}
</style>

<script>
export default {
    data() {
        return {
            links: [],
            state1: '',
            state2: ''
        };
    },
    methods: {
        querySearch(queryString, cb) {
            var links = this.links;
            var results = queryString ? links.filter(this.createFilter(queryString)) : links;
            // call callback function to return suggestions
            cb(results);
        },
        createFilter(queryString) {
            return (link) => {
                return (link.value.toLowerCase().indexOf(queryString.toLowerCase()) === 0);
            };
        },
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
        handleSelect(item) {
            console.log(item);
        }
    },
    mounted() {
        this.links = this.loadAll();
    }
}
</script>
