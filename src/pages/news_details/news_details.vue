<template>
  <div>
    <!--<div v-show="newsContent.data">
      &lt;!&ndash;v-if="index==current"&ndash;&gt;
      <h1>{{newsA.title}}</h1>
      <p class="little">
        <span v-if="newsA.date">{{newsA.date.slice(0,4)}}年
              {{newsA.date.slice(5,7)}}月
              {{newsA.date.slice(8,10)}}日
        </span>&nbsp;<span></span>
        <span>来源：{{newsA.source}}</span>
      </p>
      <div class="news2_line"></div>
      <p v-html="newsA.label_content">{{newsA.label_content}}</p>
    </div>-->
    <div class="top_back">
      <span @click=$router.go(-1)>返回</span>
    </div>
    <div class="details" ref="newsWrap">

      <h1>标题一</h1>
      <p class="little">
        <span >2018年
              05月
              05日
        </span>&nbsp;
        <span>来源：腾讯</span>
      </p>
      <div class="news2_line"></div>
      <p >经济日报-中国经济网北京5月16日讯 近日，国家卫生健康委员会发布关于征求《食品安全国家标准 调味面制品》等4项食品安全国家标准（征求意见稿）意见的函（以下简称《征求意见稿》），酝酿已久的辣条（调味面制品）国家标准进入“落地”准备阶段。

        调味面制品即是消费者常见的辣条，据业界统计约有近500亿的产值规模。经济日报-中国经济网记者注意到，从2014年年底至今，“吃包辣条冷静一下”之类的段子风靡网络，但作为一代网红食品的代表，辣条不仅是段子手的最爱，更是地方食药监部门抽检黑榜中的“常客”。

        据《新京报》早些时候报道，2015年至2017年中旬，全国有15个省份共计131家辣条生产企业的195批次辣条上了食药监局的“黑名单”。在通报的180起食品安全问题中，食品添加剂不合格是主要原因，其中菌落总数超标占68起，甜蜜素超标占30起。

        经济日报-中国经济网记者以河南省食品药品监督管理局抽检信息显示，2017年共有4批次辣条抽检不合格，不合格原因涉及菌落总局超标和霉菌超标。2018年至今，分别在食品安全抽检中检出不合格辣条食品共计33批次。

        除了是抽检黑榜中的“常客”，辣条行业还存在标准衔接不上的问题。早在2015年，由国家食品药品监督管理总局、中国科学技术协会指导，中国食品科技学会主办，中国经济网等协办的“2015年食品安全热点科学解读媒体沟通会”上，国家粮食局科学研究院粮油加工研究室副主任谭斌研究员就曾指出，辣条由于产品品类发展时间短、标准建设滞后，这是造成产业安全的关键。

        据报道，原国家食品药品监管总局于2016年11月提出调味面制品行业国家标准立项，由河南省口岸食品检验检测所、中国食品科学技术学会等机构牵头，计划用一年左右时间制定好辣条的国家标准。据参与专家透露，新标准出台后将会对辣条产业发展起到良好的规范作用。

        此外，据媒体先前报道，关于辣条使用食品添加剂的范围，各地一直存在争议，甚至出现了地方标准相互“打架”的情况。如按照宁夏的地方标准，辣条为方便食品，不得添加甜蜜素，而依据河南省地方标准，辣条执行糕点类标准，允许限量添加甜蜜素。

        对于类似问题，《征求意见稿》中标明，食品添加剂的使用应符合GB 2760中方便米面制品的规定。经济日报-中国经济网记者查询后发现，环己基氨基磺酸钠（又名甜蜜素），环己基氨基磺酸钙，最大使用量为1.6(g/kg)。

        《征求意见稿》还标明，调味面值哦应是以小麦粉和／或其他谷物粉等为主要原料，添加食用油脂等辅料，经配料、挤压熟制、成型、调味、包装等工艺加工而成具有一定韧性的即食食品。对于辣条常见的“大刀肉”等类似肉类食品名称的标注，《征求意见稿》要求标签标识中应标明产品真实属性“调味面制品”</p>
    </div>
  </div>
</template>

<script>
  import BScroll from 'better-scroll'

  export default {
    mounted(){
      this._initScroll()
    },
    methods:{
      _initScroll(){

        if(!this.pageScroll){
          this.pageScroll = new BScroll(this.$refs.newsWrap,{
            click:true,
            probeType:3
          })
          this.pageScroll.on('scroll',(pos)=>{
            let scrollY = -Math.round(pos.y)
            if(scrollY<=68){

            }
            if(scrollY>68){
              alert(200)
            }
          })
        }else {
          this.pageScroll.refresh()
        }
      },
    },
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .top_back
    width 100%
    height 50px
    background pink

  .details
    padding  1rem 0.7rem 0
    h1
      font-size 1rem
      font-weight bold
      color #232323
    .little
      margin 0.3rem 0
      font-size 0.6rem
      color #787878
    .news2_line
      width 100%
      height 1px
      background #aaa
    >p
      font-size 0.7rem
      letter-spacing 2px
      line-height 2
      text-align justify
      margin 1rem 0
</style>
