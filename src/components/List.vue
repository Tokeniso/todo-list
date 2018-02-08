<template>
    <div class="list-table">
        <h1>TODO-LIST</h1>
        <form>
            姓名：<input type="text"/>
            <br/>
            年龄：<input type="text"/>
            <br/>
            <span style="color:red">年龄必须是数字</span>
            <br/>
            <br/>
            <button type="button">添加</button>
            <button type="button">清空</button>
        </form>
        <br/>
        <table border="1">
            <thead>
            <th>序号</th>
            <th>姓名</th>
            <th>年龄</th>
            <th>操作</th>
            </thead>
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
        name:"List"
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