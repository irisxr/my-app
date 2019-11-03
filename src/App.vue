<template xmlns:v-slot="http://www.w3.org/1999/XSL/Transform">
    <div id="app">
        <input type="text" v-model="info">
        <button @click="addToDoItem()">addItem</button>
        <!--<ul>-->
        <!--<todo-item v-for="item in list" :item='item'>-->
        <!--<template v-slot:item="itemProps">-->
        <!--<span :style="{fontSize: '30px',color:itemProps.checked ?'red':'blue'}">{{item}}</span>-->
        <!--</template>-->
        <!--</todo-item>-->
        <!--</ul>-->

        <props
                name="Hello Iris"
                :isVisible="true"
                :type="type"
                :on-change="handleChange"
        >
        </props>

        <Event
                :name="name"
                @change="handleEventChange"
        >

        </Event>

        <slot-test>
            <template v-slot:item="test">
                <p>{{test}}</p>
            </template>
        </slot-test>

        <!--<data-flume v-model="personInfo" :zip-code.sync="zipCode"-->
        <!--&gt;</data-flume>-->
        <data-flume
                :person-info="personInfo"
                :zip-code="zipCode"
                @change="handlePersonInfo"
                @update:zipCode="handleZipCodeForChild"
        >
        </data-flume>
        personInfo:{{personInfo}}<br/>
        zipCode:{{zipCode}}
        <br/>
        <!--dom更新-->
        <button @click="handleName">change this.name</button>
        <button @click="handleInfo">change this.info</button>
        <button @click="handleList">change this.list</button>
        <update-dom
                :customName="customName"
                :customInfo="customInfo"
                :customList="customList">
        </update-dom>
        <!--计算属性-->
        <Computed/>
        <Computed1/>
        <!--侦听器watch-->
        <Watch/>
        <!--指令-->
        <direct/>
        <!--自定义指令-->
        <custom-directive/>
    </div>


</template>

<script>

    // import todoItem from './components/todoItem.vue'
    import props from './components/props.vue'
    import Event from './components/Event.vue'
    import slotTest from './components/slotTest.vue'
    import dataFlume from './components/dataFlume.vue'
    import updateDom from './components/updateDom.vue'
    import Computed from './components/Computed.vue'
    import Computed1 from  './components/Computed1.vue'
    import Watch from  './components/Watch.vue'
    import direct from './components/direct.vue'
    import customDirective from './components/customDirective.vue'

    export default {
        name: 'app',
        data() {
            return {
                info: '',
                list: [],
                type: 'success',
                name: '',
                personInfo: {
                    areaCode: '+86',
                    phoneNum: ''
                },
                zipCode: '',
                customName: '',
                customInfo: {
                    number: 0
                },
                customList: []

            }
        },
        methods: {
            addToDoItem() {
                this.list.push(this.info);
                this.info = ''
            },
            handleChange(val) {
                this.type = val;
            },
            handleEventChange(val) {
                this.name = val
            },
            handlePersonInfo(val) {
                this.personInfo = val
            },
            handleZipCodeForChild(val) {
                this.zipCode = val
            },
            handleName() {
                this.customName = 'world'
            },
            handleInfo() {
                this.customInfo.number += 1
            },
            handleList() {
                this.customList.push(1, 2, 3)
            }
        },

        components: {
            // todoItem,
            props,
            Event,
            slotTest,
            dataFlume,
            updateDom,
            Computed,
            Computed1,
            Watch,
            direct,
            customDirective
        }
    }
</script>

<style>

</style>
