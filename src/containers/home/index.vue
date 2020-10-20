<template>
  <div>
    <div class="head">
        <div class="head-one">
            <img :src="logo" alt="" class="head-one-img">
            <span>办公系统</span>
        </div>
        <div class="head-two">
            <img :src="fangzi" alt="" class="head-two-fangzi">
            <input type="text" placeholder="请输入你要搜索的内容...">
            <button>搜索</button>
        </div>
        <div class="head-three">

        </div>
        <div class="head-four" v-for="item in departmentList" :key="item">
            <div class="head-four-welcome">欢迎您，（{{item.department}}）{{item.name}}</div>
            <div>
                <img :src="set" alt="">
            </div>
            <div>
                <img :src="exit" alt="">
            </div>
        </div>
    </div>



    <div class="body">
        <div class="body-left">
            <div class="body-left-one">
                <div class="body-left-one-left">
                    <img :src="touxiang" alt="">
                </div>
                <div class="body-left-one-right" v-for="item in departmentList" :key="item">
                    <div class="body-left-one-right-up">{{item.name}}</div>
                    <div class="body-left-one-right-down">{{item.englishName}}</div>
                </div>
            </div>
            <div class="body-left-two" v-for="item in departmentList" :key="item">
                <div class="body-left-two-left">
                    <div>职务(Duties) :</div>
                    <div>{{item.duties}}</div>
                </div>
                <div class="body-left-two-right">
                    <div>部门(Department) :</div>
                    <div>{{item.department}}</div>
                </div>
            </div>
            <div class="body-left-three" v-for="(item,index) in tabList" :key="index">
                <div>
                    <img :src="item.url" alt />
                    {{item.name}}
                </div>
            </div>
            <div class="body-left-four"></div>
        </div>
        <div class="body-right"></div>
    </div>
  </div>
</template>

<script>
export default {
    name:'test',
    components:{},
    data(){
        return{
            logo:require('@/assets/image/logo.png'),
            fangzi:require('@/assets/image/fangzi.png'),
            set:require('@/assets/image/shezhi.png'),
            exit:require('@/assets/image/tuichu.png'),
            touxiang:require('@/assets/image/touxiang.jpg'),
            departmentList:this.getDepartmentList(),
            // tabList:this.getTabList(),
        }
    },
    methods:{
        getDepartmentList(){
            return[
                {
                    id:1,
                    name:'张丽娜',
                    englishName:'Zhang Lina',
                    duties:'平面设计',
                    department:'综合管理部'
                }
            ]
        },
        getTabList(){
            return[
                {
                    id:1,
                    url:relquire('@/assets/image/icon1.png'),
                    name:'个人中心',
                },
            ]
        }
    }
}
</script>

<style lang="less">
.head{
    padding: 0 10% 0 10%;
    // background-color: skyblue;
    // width: 80%;
    margin: 0 auto 0 auto;
    display: flex;
    justify-content: space-around;
    &-one{
        font-size: 25px;
        margin: 20px 0 0 0;
        &-img{
            transform: translate(0,10px);
        }
    }
    &-two{
        margin: 20px 0 0 0;
        &-fangzi{
            transform: translate(0,10px);
        }
    }
    &-three{
        width: 17%;
    }
    &-four{
        display: flex;
        &-welcome{
        margin: 30px 0 0 0;
        }
    }
}
.body{
    padding: 20px 10% 20px 10%;
    background-color: skyblue;
    width: 350px;
    &-left{
        border-radius: 10px;
        background-color: white;
        &-one{
            display: flex;
            justify-content: center;
            padding: 20px 0 20px 0;
            &-right{
                margin:25px 0 0 15px;
                &-down{
                    color: gray;
                }
            }
        }
        &-two{
            display: flex;
            justify-content: space-between;
            text-align: center;
            line-height: 30px;
            &-left{
                border: 1px solid rgb(235, 230, 230);
                padding: 10px 0 10px 0;
                width: 49%;
                height: 60px;
            }
            &-right{
                border: 1px solid rgb(235, 230, 230);
                width: 49%;
                padding: 10px 0 10px 0;
                height: 60px;
            }
        }
    }
}

</style>