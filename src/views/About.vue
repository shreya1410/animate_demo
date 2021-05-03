<template>
  <div class="about">
    <transition appear
    @before-enter="beforeEnter"
                @enter="enter"
                @after-enter="afterEnter"
    >
<!--                @after-enter="afterEnter" -->
<!--                @before-leave="beforeLeave"-->
<!--                @leave="leave"-->
<!--                @after-leave="afterLeave"-->

    <h1 v-if="showTitle">About</h1>
    </transition>
    <p>Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Even the all-powerful Pointing has no control about the blind texts it is an almost unorthographic life One day however a small line of blind text by the name of Lorem Ipsum decided to leave for the far World of Grammar. She packed her seven versalia, put her initial into the belt and made herself on the way. When she reached the first hills of the Italic Mountains, she had a last view back on the skyline of her hometown Bookmarksgrove, the headline of Alphabet Village and the subline of her own road, the Line Lane</p>
    <p>The quick, brown fox jumps over a lazy dog. DJs flock by when MTV ax quiz prog. Junk MTV quiz graced by fox whelps. Bawds jog, flick quartz, vex nymphs. Waltz, bad nymph, for quick jigs vex! Fox nymphs grab quick-jived waltz. Brick quiz whangs jumpy veldt fox. Bright vixens jump; dozy fowl quack. Quick wafting zephyrs vex bold Jim. Quick zephyrs blow, vexing daft Jim.</p>
    <p>A wonderful serenity has taken possession of my entire soul, like these sweet mornings of spring which I enjoy with my whole heart. I am alone, and feel the charm of existence in this spot, which was created for the bliss of souls like mine. I am so happy, my dear friend, so absorbed in the exquisite sense of mere tranquil existence, that I neglect my talents. I should be incapable of drawing a single stroke at the present moment; and yet I feel that I never was a greater artist than now.</p>
  </div>

</template>

<script>
import {ref} from 'vue'
import gsap from 'gsap'

export default {
  setup() {
    const showTitle = ref(true)
    const beforeEnter = (el) => {
      console.log('before enter -  set initial state')
      el.style.transform = 'translateY(-60px)'
      el.style.opacity =0
    }
    const enter = (el ,done) => {
     console.log('starting to enter ')
      gsap.to(el, {
        duration:3,
        y: 0,
        opacity:1,
        ease :'bounce.out',
        onComplete:done
      })
    }
    const afterEnter = ()  => {
     console.log('after enter')
    }
    // const afterEnter = (el) => {
    //   el.style.color='green'
    //   console.log('after enter' ,el)
    //   setTimeout(() => showTitle.value = false, 2000 )
    // }
    // const beforeLeave = (el) => {
    //   el.style.color='red'
    //   console.log('before leave' ,el)
    // }
    // const leave = (el) => {
    //   console.log('leave' ,el)
    // }
    // const afterLeave = (el) => {
    //   console.log('after leave' ,el)
    // }
    return { showTitle, beforeEnter, enter , afterEnter }
  }


}
</script>

<style>
  .about {
    max-width: 600px;
    margin: 20px auto;
  }
  /*.fade-enter-from{*/
  /*  opacity: 0;*/
  /*}*/
  /*.fade-enter-active{*/
  /*  transition: opacity 3s ease;*/
  /*}*/
  /*.fade-leave-to{*/
  /*  opacity: 0;*/
  /*}*/
  /*.fade-leave-active{*/
  /*  transition: opacity 3s ease;*/
  /*}*/
</style>