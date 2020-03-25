<template>
  <div>
    <div class="clock">
      <div class="hour">
        <div
        :class="hrClass"
        class="hr" id="hr"></div>
      </div>
      <div class="min">
        <div
        :class="mnClass" 
        class="mn" id="mn"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    hour: String,
    minute: String,
    style: String,
    uid: String 
  },
  data(){
      return {
          hrClass: this.uid+'hr',
          mnClass: this.uid+'mn'

      }
  },
  mounted() {

    const clock = document.querySelector(".clock");  
    clock.style = `${this.style}`;
    const deg = 6;
    const offset = 180;

    console.log(this.hrClass);
        console.log(this.mnClass);
    const hr = document.querySelectorAll("." + this.hrClass);
    const mn = document.querySelectorAll("." + this.mnClass);

    // const hr = document.querySelector("#hr");
    // const mn = document.querySelector("#mn");
    setInterval(() => {
      //let day = new Date();
      let hh = this.hour * 30;
      let mm = this.minute * deg;
    //   let hh = day.getHours() * 30;
    //   let mm = day.getMinutes() * deg;
      //console.log(" h: "+day.getHours()+" m: "+ day.getMinutes());
      hr.style.transform = `rotateZ(${hh + mm / 12 + offset}deg)`;
      mn.style.transform = `rotateZ(${mm + offset}deg)`;
    });
  }
};
</script>

<style scoped lang="scss">
.clock {
    position: absolute;
    left: 0%;
    top: 0%;
  width: 350px;
  height: 350px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: grey;
  border-radius: 50%;
  border: 20px solid grey;
  box-shadow: inset 0 0 30px rgba(0, 0, 0, 0.1), 0 20px 20px rgba(0, 0, 0, 0.2),
    0 0 0 4px rgba(255, 255, 255, 1);
}
.clock::before {
  content: "";
  position: absolute;
  width: 15px;
  height: 15px;
  background: #848484;
  border: 2px solid #fff;
  z-index: 1000000;
  border-radius: 50%;
}
.hour,
.min {
  position: absolute;
}

.hour,
.hr {
  //needs to be changed to be same lenght as min
  width: 160px;
  width: 160px;
}

.min,
.mn {
  width: 190px;
  width: 190px;
}

.hr,
.mn {
  display: flex;
  justify-content: center;
  position: absolute;
  border-radius: 50%;
}
.hr::before {
  content: "";
  position: absolute;
  width: 8px;
  height: 80px;
  background: red;
}
.mn::before {
  content: "";
  position: absolute;
  width: 6px;
  height: 90px;
  background: white;
}
</style>
