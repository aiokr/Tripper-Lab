<script>

const hi8ImgUrl = "https://stars.tripper.press/api/himawari8"
const fy4aChinaImgUrl = "https://img.nsmc.org.cn/CLOUDIMAGE/FY4A/MTCC/FY4A_CHINA.JPG"
const fy4aDiskImgUrl = "http://img.nsmc.org.cn/CLOUDIMAGE/FY4A/MTCC/FY4A_DISK.JPG"

export default {
  name: 'starImg',
  data() {
    return {
      hi8Img: { backgroundImage: "url(" + hi8ImgUrl + ")" },
      fy4aChinaImg: { backgroundImage: "url(" + fy4aChinaImgUrl + ")" },
      fy4aDiskImg: { backgroundImage: "url(" + fy4aDiskImgUrl + ")" },
    }
  },
  mounted() {
    setInterval(() => {
      let mm = new Date().getMonth() + 1;
      let dd = new Date().getDate();
      let hh = new Date().getHours();
      let mf = new Date().getMinutes() < 10 ? '0' + new Date().getMinutes() : new Date().getMinutes();
      var time = mm + dd + hh + mf
      console.log(time)
      this.hi8Img.backgroundImage = "url(" + hi8ImgUrl + "?" + time + ")";
      this.fy4aChinaImg.backgroundImage = "url(" + fy4aChinaImgUrl + "?" + time + ")";
      this.fy4aDiskImg.backgroundImage = "url(" + fy4aDiskImgUrl + "?" + time + ")";
      console.log('Image is change')
    }, 600000);
  },
}
</script>

<template>
  <main>
    <section id="hi8" class="hi8sect grid grid-cols-12 h-screen p-12">
      <div class="content-area col-span-6">
      </div>
      <div class="hi8Img starimgarea col-span-6" :style="hi8Img">
      </div>
    </section>
    <section id="fy4aChina" class="fy4aChinaSect h-screen">
      <div class="fy4aChinaImg starimgarea h-full w-full" :style="fy4aChinaImg">
      </div>
    </section>
    <section id="fy4ADisk" class="4aDiskSect grid grid-cols-12 h-screen p-12">
      <div class="content-area col-span-3"></div>
      <div class="fy4aDiskImg starimgarea col-span-6" :style="fy4aDiskImg">
      </div>
      <div class="content-area col-span-3"></div>
    </section>
  </main>
</template>
<style scoped>
.starimgarea {
  background-position: center;
  background-size: contain;
  background-repeat: no-repeat;
  transition: all 10s ease-in-out;
}

.fy4aChinaImg {
  background-size: cover;
}

.fy4aDiskImg {
  border-radius: 50%;
  aspect-ratio: 1 / 1;
}
</style>
