<template>
<el-container>
  <el-header>

    <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal">

      <el-menu-item index="1">Kalibry</el-menu-item>

      <el-submenu index="2">
        <template slot="title">Archivo</template>

        <el-submenu index="2-4">
          <template slot="title">Nuevo</template>
          <el-menu-item index="2-4-1">Libro</el-menu-item>
          <el-menu-item index="2-4-2">Historia</el-menu-item>
          <el-menu-item index="2-4-3">Tema</el-menu-item>
        </el-submenu>

        <el-menu-item index="2-1">Compartir</el-menu-item>
        <el-menu-item index="2-2">Cambiar de nombre</el-menu-item>
        <el-menu-item index="2-3">Publicar en la Web</el-menu-item>
        <el-menu-item index="2-4">Mover a la papelera</el-menu-item>
      </el-submenu>


      <el-submenu index="3">
        <template slot="title">Editar</template>
        <el-menu-item index="3-1"><i class="el-icon-back"></i>Deshacer</el-menu-item>
        <el-menu-item index="3-2"><i class="el-icon-right"></i>Rehacer</el-menu-item>
        <el-menu-item index="3-3"><i class="el-icon-scissors"></i>Cortar</el-menu-item>
        <el-menu-item index="4-3">Copiar</el-menu-item>
        <el-menu-item index="4-3">Pegar</el-menu-item>
        <el-menu-item index="4-3">Eliminar</el-menu-item>
        <el-menu-item index="4-3">Seleccionar todo</el-menu-item>
        <el-menu-item index="4-3">Buscar y sustituir</el-menu-item>

      </el-submenu>


      <el-submenu index="4">
        <template slot="title">Ver</template>
        <el-menu-item index="4-1">item one</el-menu-item>
        <el-menu-item index="4-2">item two</el-menu-item>
        <el-menu-item index="4-3">item three</el-menu-item>
        <el-submenu index="4-4">
          <template slot="title">item four</template>
          <el-menu-item index="4-4-1">item one</el-menu-item>
          <el-menu-item index="4-4-2">item two</el-menu-item>
          <el-menu-item index="4-4-3">item three</el-menu-item>
        </el-submenu>
      </el-submenu>


      <el-submenu index="5">
        <template slot="title">Insertar</template>
        <el-menu-item index="5-1">item one</el-menu-item>
        <el-menu-item index="5-2">item two</el-menu-item>
        <el-menu-item index="5-3">item three</el-menu-item>
        <el-submenu index="5-4">
          <template slot="title">item four</template>
          <el-menu-item index="5-4-1">item one</el-menu-item>
          <el-menu-item index="5-4-2">item two</el-menu-item>
          <el-menu-item index="5-4-3">item three</el-menu-item>
        </el-submenu>
      </el-submenu>


      <el-submenu index="6">
        <template slot="title">Formato</template>
        <el-menu-item index="6-1">item one</el-menu-item>
        <el-menu-item index="6-2">item two</el-menu-item>
        <el-menu-item index="6-3">item three</el-menu-item>
        <el-submenu index="6-4">
          <template slot="title">item four</template>
          <el-menu-item index="6-4-1">item one</el-menu-item>
          <el-menu-item index="6-4-2">item two</el-menu-item>
          <el-menu-item index="6-4-3">item three</el-menu-item>
        </el-submenu>
      </el-submenu>


      <el-submenu index="7">
        <template slot="title">Estilos</template>
        <el-menu-item index="7-1">item one</el-menu-item>
        <el-menu-item index="7-2">item two</el-menu-item>
        <el-menu-item index="7-3">item three</el-menu-item>
        <el-submenu index="7-4">
          <template slot="title">item four</template>
          <el-menu-item index="7-4-1">item one</el-menu-item>
          <el-menu-item index="7-4-2">item two</el-menu-item>
          <el-menu-item index="7-4-3">item three</el-menu-item>
        </el-submenu>
      </el-submenu>

      <el-submenu index="8">
        <template slot="title">Tabla</template>
        <el-menu-item index="8-1">item one</el-menu-item>
        <el-menu-item index="8-2">item two</el-menu-item>
        <el-menu-item index="8-3">item three</el-menu-item>
        <el-submenu index="8-4">
          <template slot="title">item four</template>
          <el-menu-item index="8-4-1">item one</el-menu-item>
          <el-menu-item index="8-4-2">item two</el-menu-item>
          <el-menu-item index="8-4-3">item three</el-menu-item>
        </el-submenu>
      </el-submenu>


      <el-submenu index="9">
        <template slot="title">Formulario</template>
        <el-menu-item index="9-1">item one</el-menu-item>
        <el-menu-item index="9-2">item two</el-menu-item>
        <el-menu-item index="9-3">item three</el-menu-item>
        <el-submenu index="9-4">
          <template slot="title">item four</template>
          <el-menu-item index="9-4-1">item one</el-menu-item>
          <el-menu-item index="9-4-2">item two</el-menu-item>
          <el-menu-item index="9-4-3">item three</el-menu-item>
        </el-submenu>
      </el-submenu>


      <el-submenu index="10">
        <template slot="title">Herramientas</template>
        <el-menu-item index="10-1">item one</el-menu-item>
        <el-menu-item index="10-2">item two</el-menu-item>
        <el-menu-item index="10-3">item three</el-menu-item>
        <el-submenu index="10-4">
          <template slot="title">item four</template>
          <el-menu-item index="10-4-1">item one</el-menu-item>
          <el-menu-item index="10-4-2">item two</el-menu-item>
          <el-menu-item index="10-4-3">item three</el-menu-item>
        </el-submenu>
      </el-submenu>


      <el-submenu index="11">
        <template slot="title">Ayuda</template>
        <el-menu-item index="11-1">item one</el-menu-item>
        <el-menu-item index="11-2">item two</el-menu-item>
        <el-menu-item index="11-3">item three</el-menu-item>
        <el-submenu index="11-4">
          <template slot="title">item four</template>
          <el-menu-item index="11-4-1">item one</el-menu-item>
          <el-menu-item index="11-4-2">item two</el-menu-item>
          <el-menu-item index="11-4-3">item three</el-menu-item>
        </el-submenu>
      </el-submenu>

    </el-menu>
     <!-- DOC ICONS-->
    <el-menu :default-active="activeIndex" class="el-menu-edit" mode="horizontal">
      <el-menu-item index="13"><i class="el-icon-back"></i></el-menu-item>
      <el-menu-item index="14"><i class="el-icon-right"></i></el-menu-item>
      <el-menu-item index="15"><i class="material-icons">spellcheck</i></el-menu-item>
      <el-menu-item index="16" id="format">
          <el-select v-model="value" placeholder="Select">
          <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value"
            :disabled="item.disabled">
          </el-option>
        </el-select>
      </el-menu-item>

      <el-menu-item index="17" id="size">
        <el-select v-model="value" placeholder="14">
        <el-option-group
          v-for="group in options"
          :key="group.label"
          :label="group.label">
          <el-option
            v-for="item in group.options"
            :key="item.value"
            :label="item.label"
            :value="item.value">
          </el-option>
        </el-option-group>
      </el-select>
      </el-menu-item>


      <el-menu-item index="18"><i class="material-icons">format_bold</i></el-menu-item>
      <el-menu-item index="19"><i class="material-icons">format_italic</i></el-menu-item>
      <el-menu-item index="20"><i class="material-icons">format_underlined</i></el-menu-item>
      <el-menu-item index="21"><i class="material-icons">format_color_text</i></el-menu-item>
      <el-menu-item index="22"><i class="material-icons">border_color</i></el-menu-item>

      <el-menu-item index="23"><i class="material-icons">add_comment</i></el-menu-item>
      <el-menu-item index="24"><i class="material-icons">insert_photo</i></el-menu-item>

      <el-menu-item index="25"><i class="material-icons">format_align_left</i></el-menu-item>
      <el-menu-item index="26"><i class="material-icons">format_align_center</i></el-menu-item>
      <el-menu-item index="30"><i class="material-icons">format_align_justify</i></el-menu-item>
      <el-menu-item index="31"><i class="material-icons">format_align_right</i></el-menu-item>

      <el-menu-item index="32"><i class="material-icons">format_list_numbered</i></el-menu-item>
      <el-menu-item index="33"><i class="material-icons">format_list_bulleted</i></el-menu-item>
      <el-menu-item index="34"><i class="material-icons">format_indent_decrease</i></el-menu-item>
      <el-menu-item index="35"><i class="material-icons">format_indent_increase</i></el-menu-item>

      <el-menu-item index="36"><i class="material-icons">create</i></el-menu-item>
      <el-menu-item index="37">
        <el-button type="primary" size="mini">Compartir</el-button>
      </el-menu-item>
    </el-menu>
  </el-header>

  <div class="papper-container">

    <div class="papper" contenteditable></div>

  </div>
</el-container>
</template>

<style scoped>

  .papper{
    width: 58%;
    height: 900px;
    background: blue;
    padding: 5%;
    margin: auto;
    background-color: white;
    border: none;
    outline: none;
    text-align: justify;
    text-decoration: none;
    letter-spacing: 3px;
    word-spacing: 10px;
    word-break: break-all;
    font-size: 14pt;
    -webkit-box-shadow: 0px 0px 5px 1px rgba(189,195,199,1);
    -moz-box-shadow: 0px 0px 5px 1px rgba(189,195,199,1);
    box-shadow: 0px 0px 5px 1px rgba(189,195,199,1);
  }

  .papper-container{
    height: 500px;
    padding: 50px;
    padding-top: 0;
    padding-bottom: 0;
    box-sizing: border-box;
    position: relative;
    margin-top: 5%;
    background-color: white;
    width: 100%;
    overflow-y: auto;
  }

  .el-container{
    width: 100%;
    height: auto;
    position: relative;
  }
  .el-header{
    width: 100%;
    padding: 0;
  }

  .el-menu-edit{
    width: 100%;
  }
  .el-menu-edit .el-menu-item{
    /* background: blue; */
    margin: auto;
    width: 50px;
  }
  .el-menu-edit #format{
    width: 180px;
  }
  .el-menu-edit #size{
    width: 105px;
  }
</style>
