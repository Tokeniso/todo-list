<template>
    <div class="list-table">
        <h1>TODO-LIST</h1>
        <form>
            姓名：<input type="text" v-model="name"/> {{name}}
            <br/>
            年龄：<input type="text" v-model="age"/>  {{age}}
            <br/>
            <span style="color:red" v-if="!isAge">年龄必须是数字</span>
            <br/>
            <br/>
            <button type="button" @click="addList">添加</button>
            <button type="button" @click="init()">清空</button>
        </form>
        <br/>
        <table border="1">
            <thead>
                <th>序号</th>
                <th>姓名</th>
                <th>年龄</th>
                <th>操作</th>
            </thead>
            <tr v-for="(data,index) in  list">
                <td>{{index+1}}</td>
                <td>{{data.name}}</td>
                <td>{{data.age}}</td>
                <td><button @click="delList(index)">删除</button></td>
            </tr>
            <tr>
                <td>1</td>
                <td>张三</td>
                <td>20</td>
                <td><button>删除</button></td>
            </tr>
            <tr>
                <td>2</td>
                <td>李四</td>
                <td>22</td>
                <td><button>删除</button></td>
            </tr>
            <tr>
                <td>3</td>
                <td>姓名</td>
                <td>29</td>
                <td><button>删除</button></td>
            </tr>
        </table>
    </div>
</template>

<script>
    export default {
        name:"TODOList",
        props:["list"],
        data () {
            return {
                //姓名
                name:"",
                //年龄
                age:"",
                //age是数字
                isAge:true
            }
        },
        methods:{
            /**
             * 列表添加数据
             * @returns {boolean}
             */
            addList:function(){
                if(!this.isAge){
                    return false;
                }
                if(this.name && this.age){
                    this.list.push({
                        name:this.name,
                        age:this.age
                    });
                    this.init();
                }
            },
            /**
             * 列表删除数据
             * @param index  list键值
             */
            delList:function(index){
                if(this.list[index] != undefined){
                    this.list.splice(index,1);
                }
            },
            /**
             * 初始化输入
             */
            init:function(){
                this.name = "";
                this.age = "";
                this.isAge = true;
            },
            /**
             * 检测数字
             * @param theObj       要检测的字符串
             * @returns {boolean}  是数字放回true  不是返回false
             */
            checkNumber:function(theObj) {
                var reg = /^[0-9]+$/;
                if(reg.test(theObj)){
                    return true;
                };
                return false;
            }
        },
        watch:{
            age:{
                /**
                 * 监听age的变化
                 * @param newValue
                 * @param oldValue
                 * @returns {boolean}
                 */
                handler(newValue, oldValue){
                    if(newValue == ""){
                        this.isAge = true;
                        return true;
                    }
                    var res = this.checkNumber(newValue);
                    if(res){
                        this.isAge = true;
                    }else{
                        this.isAge = false;
                    }
                }
            }
        }
    }
</script>

<style>
    .list-table{
        width: 100%;
    }
    .list-table table{
        margin: 0 auto;
        width: 500px;
    }
    .list-table table th{
        font-size: 28px;
    }
    .list-table table td{
        padding: 5px 0;
        font-size: 20px;
    }
</style>