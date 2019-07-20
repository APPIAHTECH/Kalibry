<template>
<el-container>

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
            <el-carousel :interval="5000" arrow="always">
                <el-carousel-item v-for="item in 4" :key="item">
                    <h3>{{ item }}</h3>
                </el-carousel-item>
            </el-carousel>
        </el-main>

    </el-container>

</el-container>
</template>

<style>
#search {
    width: 62%;
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

.time {
    font-size: 13px;
    color: #999;
}

.bottom {
    margin-top: 13px;
    line-height: 12px;
}

.button {
    padding: 0;
    float: right;
}

.image {
    width: 100%;
    display: block;
}

.clearfix:before,
.clearfix:after {
    display: table;
    content: "";
}

.clearfix:after {
    clear: both
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
