<template>
  <div class="container">
    <Carousel v-if="!hideCarousel" ref="carouselRef" v-model="currentSlide" v-bind="carouselConfig">
      <Slide >
        <div class="flex flex-col">
          <div class="w-full px-4 py-5 border border-gray-200 rounded-lg">
            <p>
              Đã 1 tuần trôi qua, mình vẫn nhớ như in ngày hôm đó. Một cô gái xinh đẹp, dễ thương ở bên cạnh mình trò chuyện và ăn bánh sinh nhật.
            </p>
            <div class="flex justify-end mt-2">
              <div @click="next" class="opacity-60 cursor-pointer">
                >>
              </div>
            </div>
          </div>
          <div class="flex justify-end">
            <img class="tuan" width="150" src="../assets/images/hanh-phuc.png" alt="">
          </div>
        </div>
      </Slide>
      <Slide >
        <div class="flex flex-col">
          <div class="w-full px-4 py-5 border border-gray-200 rounded-lg">
            <p>
              Và những món quà làm mình đi từ bất ngờ này đến bất ngờ khác. Thực sự lâu lắm rồi mình mới có được những cảm xúc như vậy. Đó là một trong những ngày đáng nhớ nhất của mình.
            </p>
            <div class="flex justify-end mt-2">
              <div @click="next" class="opacity-60 cursor-pointer">
                >>
              </div>
            </div>
          </div>
          <div class="flex justify-end">
            <img class="tuan" width="150" src="../assets/images/hanh-phuc.png" alt="">
          </div>
        </div>
      </Slide>
      <Slide >
        <div class="flex flex-col">
          <div class="w-full px-4 py-5 border border-gray-200 rounded-lg">
            <p>
              Những khoảnh khắc vui vẻ, những lời tâm sự, những cái ôm ấm áp và những điều hạnh phúc mà lần đầu tiên mình cảm nhận được. Lúc đó mình đã ước thời gian có thể dừng lại
            </p>
            <div class="flex justify-end mt-2">
              <div @click="next" class="opacity-60 cursor-pointer">
                >>
              </div>
            </div>
          </div>
          <div class="flex justify-end mt-2">
            <img class="tuan" width="150" src="../assets/images/hun-gio.png" alt="">
          </div>
        </div>
      </Slide>
      <Slide >
        <div class="flex flex-col">
          <div class="w-full px-4 py-5 border border-gray-200 rounded-lg">
            <p>
              Và mình cũng đã tự nhủ rằng mình phải cố gắng nhiều hơn nữa, để chúng mình có thể cùng nhau trải qua những khoảnh khắc tuyệt vời như vậy trong tương lai.
            </p>
            <div class="flex justify-end mt-2">
              <div @click="next" class="opacity-60 cursor-pointer">
                >>
              </div>
            </div>
          </div>
          <div class="flex justify-end mt-2">
            <img class="tuan" width="150" src="../assets/images/co-gang.png" alt="">
          </div>
        </div>
      </Slide>
      <Slide >
        <div class="flex flex-col">
          <div class="w-full px-4 py-5 border border-gray-200 rounded-lg">
            <p>
              Thế nhưng tuần đầu tiên không được suôn sẻ, mình đã làm Tuyết buồn nhiều lần và đã không ở bên cạnh Tuyết. Mình cảm thấy có lỗi lắm.
            </p>
            <div class="flex justify-end mt-2">
              <div @click="next" class="opacity-60 cursor-pointer">
                >>
              </div>
            </div>
          </div>
          <div class="flex justify-end mt-2">
            <img class="tuan" width="150" src="../assets/images/nghiem-tuc.png" alt="">
          </div>
        </div>
      </Slide>
      <Slide >
        <div class="flex flex-col">
          <div class="w-full px-4 py-5 border border-gray-200 rounded-lg">
            <p>
              Mình chỉ mong rằng Tuyết sẽ cho mình cơ hội để thấu hiểu và quan tâm Tuyết nhiều hơn. Nhéeee 🥺
            </p>
            <div class="flex justify-end mt-2">
              <div @click="hideCarousel = true" class="opacity-60 cursor-pointer">
                >>
              </div>
            </div>
          </div>
          <div class="flex justify-end mt-2">
            <img class="tuan" width="150" src="../assets/images/xuc-dong.png" alt="">
          </div>
        </div>
      </Slide>
    </Carousel>

    <div v-else-if="!hideQuestion">
      <h3 class="text-2xl font-bold text-center mb-6">Toét có đồng ý không?</h3>
      <div class="flex justify-center items-center gap-4 mb-6 mt-16">
        <button 
          @click="handleAgree"
          :style="{ transform: 'scale(' + agreeButtonSize + ')' }"
          class="bg-green-500 hover:bg-green-600 text-white font-bold py-3 px-6 rounded-lg transition-all duration-300 ease-in-out"
        >
          Đồng ý
        </button>
        
        <button 
          v-if="showDisagreeButton"
          @click="handleDisagree"
          class="bg-red-500 hover:bg-red-600 text-white font-bold py-3 px-6 rounded-lg transition-all duration-300"
        >
          Không
        </button>
      </div>  
    </div>

    <div v-else>
      <h3 class="text-2xl font-bold text-center mb-6">Yeah biết là vậy mà</h3>
      <p class="text-center mb-3">Hãy nói chuyện này cho mình nhé ❤️</p>
      <a class="flex justify-center text-center" href="https://m.me/100027451190485">
        <button class="py-3 px-2 border border-gray-200 rounded-lg shadow-md" type="button">
          Okkk
        </button>
      </a>
      <div class="flex justify-center mt-2">
        <img class="tuan" width="150" src="../assets/images/an-mung.png" alt="">
      </div>
    </div>
  </div>
</template>

<script setup>
import 'vue3-carousel/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import { ref } from 'vue'

const carouselRef = ref()
const currentSlide = ref(0)
const hideCarousel = ref(false)
const hideQuestion = ref(false)

const next = () => carouselRef.value.next()
const prev = () => carouselRef.value.prev()

const carouselConfig = {
  itemsToShow: 1,
  wrapAround: false,
  mouseDrag: false,
  slideEffect: 'fade',
  touchDrag: false,
}

const clickCount = ref(0)
    const agreeButtonSize = ref(1)
    const showDisagreeButton = ref(true)
    
    const handleDisagree = () => {
      if (clickCount.value < 6) {
        clickCount.value++
        agreeButtonSize.value = 1 + (clickCount.value * 0.3)
      } else {
        showDisagreeButton.value = false
      }
    }
    
    const handleAgree = () => {
      hideQuestion.value = true
    }
</script>

<style scoped>
.tuan {
  filter: drop-shadow(1px 1px 1px white) drop-shadow(0 0 1px white);
}
</style>