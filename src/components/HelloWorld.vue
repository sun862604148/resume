<template>
  <div>
    <el-container class="container">
      <el-card class="full-card">
        <div slot="header" class="header clearfix">
          <div class="left">
            <div class="name">{{ name }}</div>
          </div>
          <div class="right" style="padding-top: 6px;">
            <div class="title">{{ title }}</div>
            <div class="title-sub">{{ title_line2 }}</div>
          </div>
          <div class="clearfix"></div>
          <hr>
          <div class="left" style="margin-top:30px;">
            <div class="content info">
              <ul>
                <li><i class="iconfont icon-user11"></i> {{ info.basic }}</li>
                <li><i class="iconfont icon-school"></i> {{ info.college }}</li>
                <li><i class="iconfont icon-jobtitle"></i> {{ info.jobs }}</li>
              </ul>
            </div>
          </div>
          <div class="right" style="margin-top:20px;">
            <div  class="content connect">
              <ul style="margin-top:24px;">
                <li>{{connect.email}} <i class="iconfont icon-email"></i></li>
                <li>{{connect.cellphone}}
                  <el-tooltip class="item" effect="light" content="请发电子邮件获取电话号码" placement="right">
                    <i class="iconfont icon-cellphone"></i>
                  </el-tooltip>
                </li>
              </ul>
            </div>
          </div>
          <div class="clearfix"></div>
        </div>
        <div style="color:#898989;margin: 20px 50px 0px">
          <Box :infolist="data.projects" />
          <Box :infolist="data.professional" />
        </div>
      </el-card>
    </el-container>
    <div class="foot">
      Created by Vue.js. Powered by mitkimi.com. All Rights Reserved
      <span>2017 ～ 2018</span>, {{ icpno }}
    </div>
  </div>
</template>

<script>
import Box from '@/components/box';

export default {
  name: 'HelloWorld',
  components: { Box },
  mounted() {
    this.showDownload();
  },
  data() {
    return {
      name: '孙永豪',
      title: '前端开发工程师',
      icpno: '鲁ICP备17056479号',
      info: {
        basic: '山东 · 烟台 / 1996.03 / 男',
        college: '山东理工大学',
        jobs: '2年前端开发工作经验',
      },
      connect: {
        web: 'https://mitkimi.com',
        gitee: 'https://gitee.com/mitkimi',
        github: 'https://github.com/mitkimi',
        segmentfault: 'https://segmentfault.com/u/mitkimi',
        email: '862604148@qq.com',
        cellphone: '157 **** 0307',
      },
      data: {
        projects: {
          title: '项目经验 - 公司',
          list: [
            {
              key: 1,
              title: 'U味儿新版CRM管理和接单系统',
              description: '使用webpack作为打包工具，前端技术栈使用react + react-router + antd等框架及库，采用前后端同构的形式满足搜索引擎内容抓取。为保证代码整洁和规范其他前端开发人员的代码习惯使用eslint Airbnb标准进行代码编写。项目结构方面，分为数据模型（model）、页面级组件（page）、公用组件（component）和工具（utility）等。（樊涛）代码托管平台：coding.net',
              urls: [
                {
                  text: 'CRM',
                  url: 'http://crm2.uweer.com',
                  type: 'success',
                },
                {
                  text: '接单系统',
                  url: 'http://waimai.uweer.com',
                  type: 'success',
                },
              ],
            },
            {
              key: 2,
              title: '对标360 duibiao360.com',
              description: '供职于对标科技时，在CTO的带头下进行了原始产品的改版。我们将UI库从Material-UI切换到and.design，同时将语法升级到ES6。并且使用了百度的echarts图表插件进行了数据可视化。该项目使用react-transmit从服务端获取数据，并在前后端同时渲染，使得搜索引擎在抓去代码时候可以获取到服务端传来的数据。代码托管平台：coding.net',
              urls: [
                {
                  text: '对标科技',
                  url: 'http://www.duibiao360.com',
                  type: '',
                },
              ],
            },
          ],
        },
        history: {
          title: '工作经历',
          list: [
            {
              key: 1,
              title: '北京快洁筷好味科技有限公司',
              description: '【2017.6至今】 - 前端开发工程师',
              urls: [],
            },
            {
              key: 2,
              title: '北京对标科技有限责任公司',
              description: '【2016.10 - 2017.5】 - 前端开发工程师',
              urls: [],
            },
          ],
        },
        professional: {
          title: '专业技能',
          list: [
            {
              key: 1,
              title: '工作平台',
              description: '熟练使用Mac、Linux GUI和Windows进行开发，熟悉H5，CSS3，熟练使用Bootstrap、jQuery、jQuery.ajax。对React.js、Vue.js情有独钟，参与过多个SaaS、系统的开发。',
              urls: [
                {
                  text: 'Mac',
                  url: '#',
                  type: 'success',
                },
                {
                  text: 'Ubuntu',
                  url: '#',
                  type: 'success',
                },
                {
                  text: 'Windows',
                  url: '#',
                  type: 'warning',
                },
              ],
            },
            {
              key: 2,
              title: '联合开发能力',
              description: '熟练使用git版本控制系统，熟练使用分支、解决冲突处理和代码merge等。',
              urls: [
                {
                  text: 'git',
                  url: '#',
                  type: 'success',
                },
                {
                  text: 'svn',
                  url: '#',
                  type: 'warning',
                },
              ],
            },
          ],
        },
      },
    };
  },
  methods: {
    showDownload() {
      this.$notify({
        title: '下载pdf版简历',
        type: 'info',
        duration: 0,
        position: 'bottom-right',
        showClose: false,
        onClick: () => {
          window.location.href = 'https://files.ipietech.net/田玉可简历-高级前端工程师.pdf';
        },
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .full-card {
    width: 100%;
  }
  .header {
    color: #fff;
    padding:15px 15px 0 15px;
  }
  .left {
    float: left;
  }
  .right {
    float: right;
    text-align:right;
  }
  .header .name {
    font-size: 48px;
  }
  .header .title {
    font-size: 22px;
  }
  .header .title-sub {
    font-size: 16px;
  }
  .header .info {
    font-size:16px;
    line-height:28px;
  }
  .clearfix {
    clear:both;
  }
  hr {
    height:0;
    width:100%;
    border:0;
    border-bottom: 1px solid rgba(255,255,255,.4);
  }
  .icon {

  }
  .icon-box {
    margin:5px 0 10px 0;
  }
  .icon-box a {
    color: #ffffff;
    text-decoration: none;
  }
  .ball {
    padding:10px 13px;
    background:rgba(0,0,0,.4);
    border-radius: 60px;
    box-shadow: 0 0 8px rgba(0,0,0,.2);
    color:#f90;
  }
  .ball:hover {
    background:rgba(0,0,0,.6);
    box-shadow: 0 0 8px rgba(0,0,0,.6);
  }
  .foot {
    color:rgba(0,0,0,.4);
    text-align: center;
    font-size:13px;
    margin-top: 20px;
    margin-bottom: 60px;
  }
</style>
