<template>
  <div class="about">
    <transition 
    appear
    @before-enter="beforeEnter" 
    @enter="enter" 
    @after-enter="afterEnter"
    @before-leave="beforeLeave"
    @leave="leave"
    @after-leave="afterLeave">
      <h1>About</h1>
    </transition>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod
      quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!
    </p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod
      quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!
    </p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod
      quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!
    </p>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity'
import gsap from 'gsap'

export default {
  setup() {
    const showTitle = ref(true)

    const beforeEnter = ((el) => {
      console.log('before enter', el)
      el.style.transform = 'translateY(-60px)'
      el.style.opacity = 0
    })
    const enter = ((el, done) => {
      console.log('enter',ElementInternals)
      gsap.to(el, {
        duration:3,
        y:0,
        opacity:1,
        ease:'bounce.out',
        onComplete: done
      })
    })
    const afterEnter = ((el) => {
      console.log(' After enter',ElementInternals)
    })
    const beforeLeave = ((el) => {
      console.log('before leave',ElementInternals)
    })
    const leave = ((el) => {
      console.log('leave',ElementInternals)
    })
    const afterLeave = ((el) => {
      console.log(' After leave',ElementInternals)
      
    })

    return { showTitle,beforeEnter, enter, afterEnter,beforeLeave, leave, afterLeave }

  }
}
</script>

<style>
.about {
  max-width: 600px;
  margin: 20px auto;
}

/* transition bout */
/* .fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.5s ease;
} */
</style>