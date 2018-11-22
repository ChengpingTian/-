<template>
    <div class="icons">
        <swiper :options="swiperOption">
            <swiper-slide v-for="(page, index) of pages" :key="index">
                <div class="icon" v-for="item of page" :key="item.id">
                    <div class='icon-img'>
                        <img class='icon-img-content' :src='item.imgUrl' />
                    </div>
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      List: [
        {
          id: 1,
          imgUrl: 'https://pics.lvjs.com.cn/pics/super/2018/09/1537503649_84824.png',
          desc: '旅行必备'
        },
        {
          id: 1,
          imgUrl: 'https://pics.lvjs.com.cn/pics/super/2017/12/1514474349_75047.png',
          desc: '自驾游'
        },
        {
          id: 1,
          imgUrl: 'https://pics.lvjs.com.cn/pics/super/2018/09/1537503649_84824.png',
          desc: '旅行必备'
        },
        {
          id: 1,
          imgUrl: 'https://pics.lvjs.com.cn/pics/super/2017/12/1514474349_75047.png',
          desc: '自驾游'
        },
        {
          id: 1,
          imgUrl: 'https://pics.lvjs.com.cn/pics/super/2018/09/1537151275_13583.png',
          desc: '超级会员'
        },
        {
          id: 1,
          imgUrl: 'https://pics.lvjs.com.cn/pics/super/2018/09/1536285284_28934.png',
          desc: '天天特价'
        },
        {
          id: 1,
          imgUrl: 'https://pics.lvjs.com.cn/pics/super/2017/12/1514474349_75047.png',
          desc: '自驾游'
        },
        {
          id: 1,
          imgUrl: 'https://pics.lvjs.com.cn/pics/super/2018/09/1537503649_84824.png',
          desc: '旅行必备'
        },
        {
          id: 1,
          imgUrl: 'https://pics.lvjs.com.cn/pics/super/2018/09/1537151275_13583.png',
          desc: '超级会员'
        }
      ],
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.List.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'

.icons >>> .swiper-container {
    height: 0;
    padding-bottom: 50%;
}

.icons {
    margin-top: 0.1rem;

    .icon {
        position: relative;
        overflow: hidden;
        float: left;
        width: 25%;
        height: 0;
        padding-bottom: 25%;

        .icon-img {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0.44rem;
            box-sizing: border-box;
            padding: 0.1rem;

            .icon-img-content {
                display: block;
                margin: 0 auto;
                height: 100%;
            }
        }

        .icon-desc {
            position: absolute;
            left: 0;
            right: 0;
            bottom: 0;
            height: 0.44rem;
            line-height: 0.44rem;
            text-align: center;
            color: $darkTextColor;
            ellipsis();
        }
    }
}
</style>
