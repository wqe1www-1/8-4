<template>
  <div id="app">
    <input class="shu" type="text" placeholder="搜索" />
    <div class="aopl">
      <div class="tuo">
        <div class="gao">
          <img class="circle-img" src="https://ts4.cn.mm.bing.net/th?id=ORMS.5c54f0eccd3db555240bef2e652c7a9c&pid=Wdp&w=300&h=156&qlt=90&c=1&rs=1&dpr=1.5&p=0" alt="图片描述" />
          <span class="zi1">爱吃肉不好吗</span>
          <span class="zi2">体验卡今日到期</span>
        </div>

        <div class="tu">
          <img src="https://ts4.cn.mm.bing.net/th?id=ORMS.242ab8f2b3064dfa82e64111c8280601&pid=Wdp&w=300&h=156&qlt=90&c=1&rs=1&dpr=1.5&p=0" />
          <img src="https://ts4.cn.mm.bing.net/th?id=ORMS.242ab8f2b3064dfa82e64111c8280601&pid=Wdp&w=300&h=156&qlt=90&c=1&rs=1&dpr=1.5&p=0" />
          <img src="https://ts4.cn.mm.bing.net/th?id=ORMS.242ab8f2b3064dfa82e64111c8280601&pid=Wdp&w=300&h=156&qlt=90&c=1&rs=1&dpr=1.5&p=0" />
          <img src="./assets/01538491ec9d60620ee0da3f1bc3f68.png" id="ywuioe" alt="" />
        </div>
      </div>
    </div>
    <div class="kuan">
      <div class="admin_top_nav">
        <div :class="color_flog == 0 ? 'admin_top_nav_color' : ''" @click="color_flog = 0">推荐</div>
        <div :class="color_flog == 1 ? 'admin_top_nav_color' : ''" @click="color_flog = 1">分类</div>
        <div :class="color_flog == 4 ? 'admin_top_nav_color' : ''" @click="color_flog = 4">排行</div>

        <div :class="color_flog == 2 ? 'admin_top_nav_color' : ''" @click="color_flog = 2">文学</div>
        <div :class="color_flog == 3 ? 'admin_top_nav_color' : ''" @click="color_flog = 3">精品小说</div>
      </div>
    </div>

    <div v-if="color_flog == 0" class="a2w">
      <div class="xiao" v-for="(item, inde) in list" :key="inde">
        <img class="imgs" :src="item.imgs" alt="" />
        <div class="ass">
          <h4>{{ item.name }}</h4>
          <p class="p">
            {{ item.zi }}<b :class="{ 'odd-row': inde % 2 === 0, 'even-row': inde % 2 !== 0 }">{{ item.ff }}</b
            ><br />
            大家都在读
          </p>
        </div>
      </div>
    </div>

    <div v-if="color_flog == 4" class="a4w">
      <div class="xiao" v-for="(item, inde) in list3" :key="inde">
        <img class="imgs" :src="item.imgs" alt="" />
        <div class="ass">
          <h6>{{ item.name }}</h6>
          <p class="p">{{ item.zi }}<br /></p>
        </div>
      </div>
      <button class="btn">查看全部</button>
    </div>

    <div v-if="color_flog == 1" class="aw3">
      <div class="xiao1" v-for="(item, inde) in list1" :key="inde">
        <img class="imgs1" :src="item.imgs" alt="" />
        <div class="ass1">
          <h4>{{ item.name }}</h4>
          <h3 class="h3">{{ item.ff }}<br />{{ item.zi }}<br />{{ item.xiangqing }}</h3>
        </div>
      </div>
    </div>

    <div v-if="color_flog == 3" class="a1w">
      <div class="xiao" v-for="(item, inde) in list" :key="inde">
        <h5 class="h5">{{ item.id }}</h5>
        <img class="imgs" :src="item.imgs" alt="" />
        <div class="ass22">
          <h4>{{ item.name }}</h4>
          <p class="p">
            {{ item.san }}
            <br />
            {{ item.zi }}<b :class="{ 'odd-row': inde % 2 === 0, 'even-row': inde % 2 !== 0 }">{{ item.ff }}</b>
          </p>
          <div class="dian">
            <img src="./assets/_我的.png" class="opp" alt="" /><b class="dianop">{{ item.dian }}</b>
          </div>
        </div>
      </div>
    </div>
    <div v-if="color_flog == 2" class="a1w">
      <div class="xiao" v-for="(item, inde) in list2" :key="inde">
        <h5 class="h5">{{ item.id }}</h5>
        <img class="imgs" :src="item.imgs" alt="" />
        <div class="ass22">
          <h4>{{ item.name }}</h4>
          <p class="p">
            {{ item.san }}
            <br />
            {{ item.zi }}<b :class="{ 'odd-row': inde % 2 === 0, 'even-row': inde % 2 !== 0 }">{{ item.ff }}</b>
          </p>
          <div class="dian">
            <img src="./assets/_我的.png" class="opp" alt="" /><b class="dianop">{{ item.dian }}</b>
          </div>
        </div>
      </div>
    </div>
    <div class="di"><img src="./assets/9eebc4672a825c0893bee5046ff419e.png" class="imhg" alt="" /></div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      that: '',
      color_flog: 0,

      list2: [
        { dian: '111.9万', san: '张嘉佳', ff: '神作', zi: '推荐值 89.9%', id: 1, name: '生灵', xiangqing: '把握三大新核污染风险违反国际法', imgs: 'https://img1.baidu.com/it/u=422078137,1307526884&fm=253&app=120&size=w931&n=0&f=JPEG&fmt=auto?sec=1689872400&t=23915a3707a4b4d0a92fef85266e4f4f' },
        {
          dian: '50.9万',
          id: 2,
          san: '大米',
          ff: '好评如潮',
          zi: '推荐值 91.0%',
          name: '树叶',
          xiangqing: '专题学习贯彻习近平新时国代首都发展巡礼李强会见美国总统气候问题特使',
          imgs: 'https://img1.baidu.com/it/u=3065838285,2676115581&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1691254800&t=ae5fdc6f03a0407251ebbf60dd2a9768'
        },
        {
          dian: '40.89万',
          id: 3,
          san: '麦家',
          ff: '神作',
          zi: '推荐值 93.4%',
          xiangqing: '国防部长李尚福会见美国前命案”系谣言西安市教育局: 网传“回了台北故宫，马英九陪同看了这些',

          name: '天空',

          imgs: 'https://img2.baidu.com/it/u=1361506290,4036378790&fm=253&fmt=auto&app=138&f=JPEG?w=800&h=500'
        },
        {
          dian: '50.9万',
          id: 4,
          san: '大米',
          ff: '好评如潮',
          zi: '推荐值 91.0%',
          name: '树叶',
          xiangqing: '专题学习贯彻习近平新时国代首都发展巡礼李强会见美国总统气候问题特使',
          imgs: 'https://img0.baidu.com/it/u=1838040407,1274103844&fm=253&fmt=auto&app=120&f=JPEG?w=1422&h=800'
        },
        {
          dian: '40.89万',
          id: 5,
          san: '麦家',
          ff: '神作',
          zi: '推荐值 93.4%',
          xiangqing: '国防部长李尚福会见美国前命案”系谣言西安市教育局: 网传“回了台北故宫，马英九陪同看了这些',

          name: '天空',

          imgs: 'https://img0.baidu.com/it/u=1838040407,1274103844&fm=253&fmt=auto&app=120&f=JPEG?w=1422&h=800'
        },
        {
          dian: '50.9万',
          id: 6,
          san: '大米',
          ff: '好评如潮',
          zi: '推荐值 91.0%',
          name: '树叶',
          xiangqing: '专题学习贯彻习近平新时国代首都发展巡礼李强会见美国总统气候问题特使',
          imgs: 'https://img2.baidu.com/it/u=3202947311,1179654885&fm=253&fmt=auto&app=138&f=JPEG?w=800&h=500'
        },
        {
          dian: '40.89万',
          id: 7,
          san: '麦家',
          ff: '神作',
          zi: '推荐值 93.4%',
          xiangqing: '国防部长李尚福会见美国前命案”系谣言西安市教育局: 网传“回了台北故宫，马英九陪同看了这些',

          name: '天空',

          imgs: 'https://img1.baidu.com/it/u=1839135015,723795615&fm=253&fmt=auto&app=138&f=JPEG?w=800&h=500'
        },
        {
          dian: '50.9万',
          id: 8,
          san: '大米',
          ff: '好评如潮',
          zi: '推荐值 91.0%',
          name: '树叶',
          xiangqing: '专题学习贯彻习近平新时国代首都发展巡礼李强会见美国总统气候问题特使',
          imgs: 'https://img1.baidu.com/it/u=1839135015,723795615&fm=253&fmt=auto&app=138&f=JPEG?w=800&h=500'
        },
        {
          dian: '40.89万',
          id: 9,
          san: '麦家',
          ff: '神作',
          zi: '推荐值 93.4%',
          xiangqing: '国防部长李尚福会见美国前命案”系谣言西安市教育局: 网传“回了台北故宫，马英九陪同看了这些',

          name: '天空',

          imgs: 'https://img1.baidu.com/it/u=624792125,331972384&fm=253&fmt=auto&app=138&f=JPEG?w=800&h=500'
        }
      ],

      list: [
        { dian: '111.9万', san: '张嘉佳', ff: '神作', zi: '推荐值 89.9%', id: 1, name: '生灵', xiangqing: '把握三大新核污染风险违反国际法', imgs: 'https://img1.baidu.com/it/u=422078137,1307526884&fm=253&app=120&size=w931&n=0&f=JPEG&fmt=auto?sec=1689872400&t=23915a3707a4b4d0a92fef85266e4f4f' },
        {
          dian: '50.9万',
          id: 2,
          san: '大米',
          ff: '好评如潮',
          zi: '推荐值 91.0%',
          name: '树叶',
          xiangqing: '专题学习贯彻习近平新时国代首都发展巡礼李强会见美国总统气候问题特使',
          imgs: 'https://img1.baidu.com/it/u=624792125,331972384&fm=253&fmt=auto&app=138&f=JPEG?w=800&h=500'
        },
        {
          dian: '40.89万',
          id: 3,
          san: '麦家',
          ff: '神作',
          zi: '推荐值 93.4%',
          xiangqing: '国防部长李尚福会见美国前命案”系谣言西安市教育局: 网传“回了台北故宫，马英九陪同看了这些',

          name: '天空',

          imgs: 'https://img1.baidu.com/it/u=624792125,331972384&fm=253&fmt=auto&app=138&f=JPEG?w=800&h=500'
        },
        {
          dian: '50.9万',
          id: 4,
          san: '大米',
          ff: '好评如潮',
          zi: '推荐值 91.0%',
          name: '树叶',
          xiangqing: '专题学习贯彻习近平新时国代首都发展巡礼李强会见美国总统气候问题特使',
          imgs: 'https://img2.baidu.com/it/u=483398814,2966849709&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1689872400&t=93a58d55db740132d64d48dcd60c8c1c'
        },
        {
          dian: '40.89万',
          id: 5,
          san: '麦家',
          ff: '神作',
          zi: '推荐值 93.4%',
          xiangqing: '国防部长李尚福会见美国前命案”系谣言西安市教育局: 网传“回了台北故宫，马英九陪同看了这些',

          name: '天空',

          imgs: 'https://img2.baidu.com/it/u=483398814,2966849709&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1689872400&t=93a58d55db740132d64d48dcd60c8c1c'
        },
        {
          dian: '50.9万',
          id: 6,
          san: '大米',
          ff: '好评如潮',
          zi: '推荐值 91.0%',
          name: '树叶',
          xiangqing: '专题学习贯彻习近平新时国代首都发展巡礼李强会见美国总统气候问题特使',
          imgs: 'https://img2.baidu.com/it/u=483398814,2966849709&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1689872400&t=93a58d55db740132d64d48dcd60c8c1c'
        },
        {
          dian: '40.89万',
          id: 7,
          san: '麦家',
          ff: '神作',
          zi: '推荐值 93.4%',
          xiangqing: '国防部长李尚福会见美国前命案”系谣言西安市教育局: 网传“回了台北故宫，马英九陪同看了这些',

          name: '天空',

          imgs: 'https://img2.baidu.com/it/u=483398814,2966849709&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1689872400&t=93a58d55db740132d64d48dcd60c8c1c'
        },
        {
          dian: '50.9万',
          id: 8,
          san: '大米',
          ff: '好评如潮',
          zi: '推荐值 91.0%',
          name: '树叶',
          xiangqing: '专题学习贯彻习近平新时国代首都发展巡礼李强会见美国总统气候问题特使',
          imgs: 'https://img2.baidu.com/it/u=483398814,2966849709&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1689872400&t=93a58d55db740132d64d48dcd60c8c1c'
        },
        {
          dian: '40.89万',
          id: 9,
          san: '麦家',
          ff: '神作',
          zi: '推荐值 93.4%',
          xiangqing: '国防部长李尚福会见美国前命案”系谣言西安市教育局: 网传“回了台北故宫，马英九陪同看了这些',

          name: '天空',

          imgs: 'https://img2.baidu.com/it/u=483398814,2966849709&fm=253&app=138&size=w931&n=0&f=JPEG&fmt=auto?sec=1689872400&t=93a58d55db740132d64d48dcd60c8c1c'
        }
      ],
      list1: [
        {
          ff: '1.长相思 (杨紫 张晚意 邓为 檀健..',
          zi: '2法医秦明 推荐值 89.9%',
          id: 1,
          name: '精品小说',
          xiangqing: '3.平凡的世界 (全三册)',
          imgs: 'https://img1.baidu.com/it/u=422078137,1307526884&fm=253&app=120&size=w931&n=0&f=JPEG&fmt=auto?sec=1689872400&t=23915a3707a4b4d0a92fef85266e4f4f'
        },
        {
          id: 2,
          ff: '1.长相思 (杨紫 张晚意 邓为 檀健..',
          zi: '2.剑来',
          name: '历史',
          xiangqing: '3.三体(全集)',
          imgs: 'https://img1.baidu.com/it/u=1699929707,733321099&fm=253&fmt=auto&app=120&f=JPEG?w=1422&h=800'
        },
        {
          id: 3,
          ff: '1.明朝那些事儿(全集)',
          zi: '2长安的荔枝',
          xiangqing: '3.商: 殷周之变与华夏新生',

          name: '文学',

          imgs: 'https://img2.baidu.com/it/u=2312383180,3750420672&fm=253&fmt=auto&app=120&f=JPEG?w=1280&h=800'
        }
      ],
      list3: [
        {
          ff: '1.长相思 (杨紫 张晚意 邓为 檀健..',
          zi: '法医秦明 推荐值 89.9%',
          id: 1,
          name: '1精品小说',
          xiangqing: '3.平凡的世界 (全三册)',
          imgs: 'https://img1.baidu.com/it/u=422078137,1307526884&fm=253&app=120&size=w931&n=0&f=JPEG&fmt=auto?sec=1689872400&t=23915a3707a4b4d0a92fef85266e4f4f'
        },
        {
          id: 2,
          ff: '1.长相思 (杨紫 张晚意 邓为 檀健..',
          zi: '.剑来',
          name: '2历史',
          xiangqing: '3.三体(全集)',
          imgs: 'https://img1.baidu.com/it/u=1699929707,733321099&fm=253&fmt=auto&app=120&f=JPEG?w=1422&h=800'
        },
        {
          id: 3,
          ff: '1.明朝那些事儿(全集)',
          zi: '长安的荔枝',
          xiangqing: '3.商: 殷周之变与华夏新生',

          name: '3文学',

          imgs: 'https://img2.baidu.com/it/u=2312383180,3750420672&fm=253&fmt=auto&app=120&f=JPEG?w=1280&h=800'
        }
      ]
    }
  },
  methods: {}
}
</script>

<style>
#ywuioe {
  width: 10%;
}
.tu {
  width: 100%;
  height: 6.25rem;
  float: left;

  margin-left: 10%;
}
.btn {
  width: 90%;
  height: 10vh;
  background: #f8f8fa;
  margin-left: 5%;
  border: none;
  margin-top: 3%;
}
.gao {
  height: 3.125rem;
}
.tu img {
  margin-right: 0.75rem;
  width: 20%;
  height: 4.375rem;
  float: left;
  object-fit: cover;
}

.aopl {
  height: 30%;
}
.circle-img {
  border-radius: 50%;
  width: 1.875rem;
  height: 1.875rem;
  object-fit: cover;
  margin-left: 10%;
  margin-top: 4%;
  float: left;
}
.zi1 {
  font-size: 13px;
  color: rgb(242, 245, 246);
  float: left;
  margin-top: 6%;
  margin-left: 3%;
}

.zi2 {
  color: rgb(156, 154, 144);
  font-size: 12px;
  float: left;
  margin-top: 6%;
  margin-left: 5%;
}
.imhg {
  width: 100%;
}
.di {
  width: 100%;
  height: 50px;
  position: fixed;
  background: #fff;
  /* top: 78.5%; */
  bottom: 0px;
  z-index: 9999;
}
.h3 {
  margin-top: -0.925rem;
  color: #a8adb4;
  font-size: 0.4125rem;
  line-height: 1.625rem;
}
.opp {
  width: 12px;
  margin-left: 10%;
  margin-top: 5%;
}
.dianop {
  margin-top: 15%;
  color: #ccc;
}
.dian {
  width: 5.075rem;
  float: right;
  height: 1.875rem;
  margin-top: -7.5rem;
  border-radius: 1.25rem;
  background: #f8f8fa;
}
h4 {
  margin-top: 3%;
  font-size: 1.05rem;
}
h6 {
  margin-top: 10%;

  font-size: 1.05rem;
}
.xiao1 {
  width: 95%;
  height: 16.5vh;
  margin: auto;
  margin-top: 5%;
  background: #f8f8fa;
  border-radius: 1.25rem;
}
.h5 {
  float: left;
  width: 7%;
  line-height: 4rem;
}
.xiao3 {
  width: 100%;
  height: 20vh;
  margin: auto;
  margin-top: 5%;
  background: #f8f8fa;
  border-radius: 1.25rem;
}
.tupian {
  float: left;
  width: 20%;
}
.tuo {
  margin: auto;
  width: 20.625rem;
  height: 10rem;
  border-radius: 0.9375rem;
  background-color: rgb(88, 89, 95);
}

.shu {
  margin-left: 14%;
  margin-bottom: 1.25rem;
  width: 18.75rem;
  height: 1.875rem;
  border-radius: 0.9375rem;
  background-color: rgb(246, 247, 249);
  color: rgb(246, 247, 249);
  border: none;
}

.p {
  width: 100%;
  margin-top: -0.925rem;
  color: #a8adb4;
  font-size: 0.9125rem;
  line-height: 2.025rem;
}
.ass1 {
  float: left;
  height: 100%;
  width: 60%;

  margin-left: 5%;
}
.ass {
  float: left;
  height: 100%;
  width: 70%;

  margin-left: 5%;
}
.ass22 {
  float: left;
  height: 100%;
  width: 68%;

  margin-left: 5%;
}
.odd-row {
  color: #c08a37;
}

.even-row {
  color: red;
}
.ass h3 {
  font-weight: 400;
}
.imgs1 {
  float: right;
  width: 30%;
  height: 100%;
  border-top-right-radius: 1.25rem;
  border-bottom-right-radius: 1.25rem;
}
.imgs {
  float: left;
  width: 20%;
  height: 100%;
}
.xiao {
  width: 95%;
  height: 14vh;
  margin: auto;
  margin-top: 5%;
}
.a2w {
  width: 100%;
  height: 100%;
  overflow: auto;
}
.a4w {
  width: 100%;
  height: 100%;
  overflow: auto;
}
.aw3 {
  width: 100%;
  height: 100%;
  overflow: auto;
}
.a1w {
  width: 100%;
  height: 90%;
  overflow: auto;
}
#app {
  width: 100%;
  height: 90vh;
}
.kuan {
  height: 8vh;
}
.admin_top_nav {
  width: 90%;

  display: flex;
  justify-content: space-between;
  margin: auto;
}
.admin_top_nav div1 {
  text-align: center;
  width: 8.4375rem;
  height: 2.25rem;
  line-height: 6.25rem;
  font-size: 1.5625rem;
}

.admin_top_nav_color {
  color: #5691ef;
}
</style>
