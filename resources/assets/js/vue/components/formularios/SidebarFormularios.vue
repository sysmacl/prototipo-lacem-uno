<template>
    <div>
        <el-aside width="fit-content">
            <el-menu default-active="4-1" class="el-menu-vertical-demo">
                <el-menu-item
                    index="1"
                    @click="inicio">
                    Inicio
                </el-menu-item>
                <el-submenu index="2">
                    <template slot="title">
                        <span slot="title">OTT</span>
                    </template>
                    <el-menu-item-group>
                        <el-menu-item index="2-1" @click="nuevaOTT">
                            Nueva OTT
                        </el-menu-item>
                        <el-menu-item index="2-2" @click="listadoOTTs">
                            OTTs por validar
                        </el-menu-item>
                        <el-menu-item index="2-3" disabled>
                            OTTs validadas
                        </el-menu-item>
                    </el-menu-item-group>
                    <!-- <el-menu-item-group>
                        <el-menu-item index="2-3" disabled>item three</el-menu-item>
                    </el-menu-item-group> -->
                    <!-- <el-submenu index="2-4">
                        <span slot="title">item four</span>
                        <el-menu-item index="2-4-1">item one</el-menu-item>
                    </el-submenu> -->
                </el-submenu>
                <el-submenu index="3">
                    <template slot="title">
                        <span slot="title">Ensayos</span>
                    </template>
                    <el-menu-item-group>
                        <el-menu-item index="3-1" @click="nuevoEnsayo">
                            Nuevo Ensayo
                        </el-menu-item>
                        <el-menu-item index="3-2" @click="listadoEnsayos">
                            Ensayos por validar
                        </el-menu-item>
                        <el-menu-item index="3-2" disabled>
                            Ensayos validados
                        </el-menu-item>
                    </el-menu-item-group>
                </el-submenu>
                <el-submenu index="4">
                    <span slot="title">Exportar</span>
                    <el-menu-item-group>
                        <el-menu-item index="4-1" @click="exportaEnsayos">
                            Ensayos
                        </el-menu-item>
                    </el-menu-item-group>
                    <!-- <el-menu-item-group>
                        <el-menu-item disabled index="4-2">
                            A Excel
                        </el-menu-item>
                    </el-menu-item-group> -->
                </el-submenu>
                <!-- <el-menu-item index="5" disabled>
                    <span slot="title">Navigator Four</span>
                </el-menu-item> -->
            </el-menu>
        </el-aside>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                isCollapse: true
            }
        },
        methods: {
            inicio(){
                this.$emit("cambiaMain", "");
            },
            nuevaOTT() {
                this.$emit("cambiaMain", {vista: "OrdenTrabajoTerreno", condicion:'nueva'});
            },
            listadoOTTs() {
                this.$emit("cambiaMain", {vista: "ListadoFormularios", condicion:''});
            },
            nuevoEnsayo() {
                this.$emit("cambiaMain", {vista: "EnsayoCompresionProbetasCilindricas", condicion:'nueva'});
            },
            listadoEnsayos() {
                this.$emit("cambiaMain", {vista: "ListadoEnsayosCompresionProbetasCilindricas", condicion:''});
            },
            exportaEnsayos() {
                this.$emit("cambiaMain", {vista: "ListadoExportarEnsayos", condicion:''});
            },
        }
    }
</script>

<style>
    .el-aside {
        background-color: #d3dce6;
        height: 100%;
        color: #333;
        text-align: left;
        overflow-x: hidden;
    }
    .el-menu-vertical-demo:not(.el-menu--collapse) {
        width: fit-content;
        min-height: 400px;
    }
    .el-menu{
        background-color: transparent;
    }
    .el-menu-item, .el-submenu__title, .el-submenu .el-menu-item {
        height: 40px;
        line-height: 40px;
    }
</style>