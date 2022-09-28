<template>
  <div class="app">
    <div class="app-container">
        <div class="app-tab">
            <div class="app-tab-header">
                <span>我的经历</span>
            </div>
            
            <div class="app-tab-container">
                <div class="app-tab-container-item"
                    v-for="(eItem, eIndex) in exps"
                    v-bind:key="eIndex"
                    v-show="eItem.list.length > 0">
                    <span>{{ eItem.name }}</span>

                    <div class="app-tab-container-item-list"
                        v-for="(item, index) in eItem.list"
                        v-bind:key="index"
                        @click="enterUrl(item.url)">
                        <div style="width: 100%; display: flex; align-item: center;"
                            v-if="index == 0">
                            <span>{{ item.name }}</span>
                            <span style="color: white; font-size: 12px; margin-left: auto; margin-right: 10px;">最新项目⭐</span>
                        </div>
                        <span v-else>{{ item.name }}</span>
                        <span>{{ item.description }}</span>
                    </div>
                </div>
                <div class="app-tab-copyright">
                    <span>© 2022 拉布拉马</span>
                </div>
            </div>
        </div>

        <div class="app-self">
            <img src="@/assets/img/logo.png">
            <span style="color: white; font-size: 25px; font-weight: bold; margin-top: 20px;">拉布拉马</span>
            <span style="color: white; font-size: 15px; margin-top: 10px;">业余编程狂热爱好者</span>
            <span style="color: white; font-size: 15px; margin-top: 30px;">欢迎访问我的个人主页</span>
            <div class="app-self-tab">
                <div class="app-self-tab-item"
                    @click="enterUrl('https://space.bilibili.com/8013472?spm_id_from=333.1007.0.0')">
                    <img src="@/assets/img/bilibili.png">
                    <span>哔哩哔哩</span>
                </div>

                <div class="app-self-tab-item"
                    @click="enterUrl('https://github.com/Tuise233/')">
                    <img src="@/assets/img/github.png">
                    <span>Github</span>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            exps: [{
                name: "主要项目",
                list: [{
                    name: "拉布拉页",
                    description: "简洁且方便的浏览器起始页",
                    url: "http://web.tuise233.cn"
                }, {
                    name: "AltV - Cloud City",
                    description: "GTA5多人联机平台AltV 角色扮演服务器项目",
                }, {
                    name: "RageMP - Freeroam County",
                    description: "GTA5多人联机平台RageMP 角色扮演服务器项目"
                }, {
                    name: "Circle Store",
                    description: "火车侠CircleUI设计前端实现",
                    url: "http://circle.tuise233.cn"
                }, {
                    name: "Bilibili Video Helper",
                    description: "哔哩哔哩视频信息获取助手",
                    url: "https://github.com/Tuise233/Bilibili-Helper"
                }, {
                    name: "Bilibili Upload Capture",
                    description: "哔哩哔哩Up主视频推送检测",
                    url: "https://github.com/Tuise233/Bilibili_Upload_Detection"
                }, {
                    name: "Blue Sky Robot",
                    description: "小栗子QQ机器人插件 兰天机器人",
                    url: "https://github.com/Tuise233/BlueSkyBot"
                }]
            }, {
                name: "工具箱",
                list: []
            }, {
                name: "小游戏",
                list: []
            }]
        }
    },

    methods: {
        enterUrl(url){
            if(url != "" && url != undefined){
                window.open(url, "_blank");
            }
        }
    },
}
</script>

<style>
.app{
    width: 100vw;
    height: 100vh;
    background-image: url("@/assets/img/bg.png");
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
}

.app-container{
    width: 100vw;
    height: 100vh;
    backdrop-filter: blur(10px);
    
    display: flex;
}

.app-tab{
    width: 400px;
    height: 100vh;
    box-shadow: inset -2px 0 5px rgba(0, 0, 0, 0.5);

    display: flex;
    flex-direction: column;
}

.app-tab-header{
    width: 100%;
    height: 45px;
    background-color: rgba(0, 0, 0, 0.15);

    display: flex;
    align-items: center;
}

.app-tab-header span{
    color: white;
    font-size: 16px;
    margin-left: 20px;
}

.app-tab-container{
    width: 380px;
    height: 100%;
    padding: 0 10px;
    margin-top: 10px;

    display: flex;
    flex-direction: column;
    overflow-y: scroll;
    overflow-x: hidden;
}

.app-tab-container-item{
    width: 100%;

    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 10px;
    padding: 10px 0;

    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.app-tab-container-item span{
    color: white;
    font-size: 15px;
    margin-bottom: 10px;
}

.app-tab-container-item-list{
    width: calc(100% - 40px);
    height: 60px;
    border-radius: 5px;
    
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin: 5px 0;

    transition: 0.3s all;
    padding: 0 20px;
}

.app-tab-container-item-list:hover{
    background-color: rgba(255, 255, 255, 0.1);
}

.app-tab-container-item-list span{
    font-size: 15px;
    color: rgb(182, 179, 179);
    margin: 2.5px 0;
}

.app-tab-container-item-list span:first-child{
    color: white;
}

.app-tab-copyright{
    width: 100%;
    margin-top: auto;
    margin-bottom: 10px;
}

.app-tab-copyright span{
    font-size: 12px;
    color: white;
}

.app-self{
    width: 100%;
    height: 100%;
    
    display: flex;
    flex-direction: column;
    align-items: center;
}

.app-self img{
    width: 150px;
    height: 150px;
    margin-top: 250px
}

.app-self-tab{
    display: flex;
    align-items: center;
    margin-top: 20px;
}


.app-self-tab-item{
    width: 100px;
    height: 30px;
    background-color: rgba(255, 255, 255, 0.1);
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 10px 10px;
    transition: 0.3s all;
    border-radius: 5px;
}

.app-self-tab-item:hover{
    background-color: rgba(255, 255, 255, 0.3);
}

.app-self-tab-item span{
    color: white;
    font-size: 14px;
}

.app-self-tab-item img{
    width: 20px;
    height: 20px;
    margin-top: 0;
    margin-right: 5px;
}
</style>