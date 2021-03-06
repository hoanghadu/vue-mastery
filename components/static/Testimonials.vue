<template lang="pug">
.testimonials
  agile.wrapper(ref='carousel' :center-mode='true' :responsive='responsive' :dots='false' :nav-buttons='false')
    .quote-box
      blockquote Vue Mastery is absolutely the best place to learn Vue, from your first version to advanced techniques. Instructors are brilliant, material is laid out perfectly for easy comprehension, and videos are high quality. I've purchased a handful of other courses and they don't even come close to Vue Mastery. Thank you guys for putting together these awesome courses!
      cite
        img(src='/images/testimonials/william-clement.jpg')
        | William C.
    .quote-box
      blockquote
        | Vue Mastery has given me a better understanding of how Vue.js works under the hood. I've been able to take the lessons I've learned and apply them to my everyday development.
        br
        | Not just the best practices, but why things work the way they do. And how to adapt my applications for future use cases.
        br
        | Vue Mastery is a must to any developer who is interested in learning more about Vue.js.
      cite
        img(src='/images/testimonials/jhillen.jpg')
        | J.D. H.
    .quote-box
      blockquote
        | Solid, consistent instructional content can be hard to find all in one place.  Many of us bounce around from platform to platform trying to piece together our own custom learning experience which helps address the actual problems we're trying to solve in the real world.  I had been attracted to the buffet style learning platforms, assuming I was getting the best bang for my buck, only to find out that more content didn't mean more helpful.  As someone who is focused on developing Vue.js solutions, Vue Mastery has the exact type of in-depth focus that allows me to further my knowledge each time new content is released.
      cite
        img(src='/images/testimonials/aaron-davidolson.jpg')
        | Aaron O.
    .quote-box
      blockquote
        | All vital information in one place, professionally presented with examples, cheat sheets. If you can't watch the video, you can read it. A truly great way how to learn a new technology not being flooded by huge amount of information when searching the Internet. I feel safe knowing that all important things I need to know about Vue.js are covered by Vue Mastery, moreover they are adding a new content regularly.
      cite
        img(src='/images/testimonials/ludvik-wiejowski.jpg')
        | Ludvik W.
    .quote-box
      blockquote Vue Mastery has helped me significantly better understand Vuex and the basics of Vue.js. I am just a beginner, but I went ahead and got a year subscription and I am so happy and satisfied that I did. Definitely worth the money and I just do the tutorials as they come out.
      cite
        img(src='/images/testimonials/tarah-perry.jpg')
        | Tarah P.
    .quote-box
      blockquote Vue Mastery has been an ideal way to learn not only Vue, but other web app and development principles. Gregg and Adam explain everything from the fundamentals to advanced concepts in a clear and methodical way, supported by funny videos and neat visuals! Money well spent!
      cite
        img(src='/images/testimonials/callum-blow.jpg')
        | Callum B.

  .controls
    .fa.fa-chevron-left(@click='$refs.carousel.goToPrev()')
    .fa.fa-chevron-right(@click='$refs.carousel.goToNext()')
</template>

<script>
import { VueAgile } from 'vue-agile'
export default {
  name: 'testimonials',
  components: {
    agile: VueAgile
  },
  data () {
    return {
      responsive: [
        {
          breakpoint: 640,
          settings: {
            slidesToShow: 2
          }
        }, {
          breakpoint: 900,
          settings: {
            slidesToShow: 3
          }
        }
      ]
    }
  },

  mounted () {
    setTimeout(() => {
      if (this.$refs.carousel) {
        this.$refs.carousel.reload()
      }
    }, 3000)
  }
}
</script>

<style lang="stylus" scoped>
.testimonials
  overflow hidden
  position relative
  z-index 2
  text-align center
  padding-top 2rem
  margin-bottom -1px

  +tablet-up()
    padding-top 5rem
    padding-bottom 3rem
    text-align left

.quote-box
  width 29rem
  max-width calc(100% + 1rem)
  font-size 16px
  color #fff
  line-height 1.6

>>> .agile__slides
  scrollbar-color $primary-color transparent
  scrollbar-width thin

>>> .agile__list
  max-width calc(100vw - 4rem)

blockquote
  font-style italic

  +tablet-up()
    padding-right 2rem
    margin 0 2rem 0 1rem
    max-height 8rem
    overflow auto

cite
  display flex
  flex-flow row
  align-items center
  justify-content center
  margin 1rem 2rem 1rem 1rem
  font-style normal

  +tablet-up()
    justify-content left

  img
    border-radius 40px
    width 50px
    margin-right 1rem
    border 1px solid #fff

.controls
  position absolute
  width 100%
  top 50%
  margin-top -3rem
  z-index 3
  display flex
  cursor pointer
  color #39b982
  justify-content space-between

  .fa
    padding 1rem
    outline none

    &:hover
      color #fff
</style>
