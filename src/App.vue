<template>
  <div id="App">
    <div class="container mt-3">
      <div class="card text-left">
            <img class="card-img-top" src="holder.js/100px180/" alt="">
            
            <div class="card-body">
              <h4 class="card-title">Generator NameTag For Physics To Image</h4>
              <!-- <p>ออกแบบเว็บไซต์และพัฒโดย นายธีรุฒ ศรีทองดี ม.5/3</p> -->
              <hr>
              <div class="form-group">
                <div class="form-group mb-3">
                  <label for="my-input" class="mb-2">เลือกคำนำหน้า</label>
                  <div class="form-check">
                    <input v-model="form.gender" type="radio" class="form-check-input" id="inlineRadio1"
                      name="type_print" value="นาย" checked="">
                    <label class="form-check-label" for="inlineRadio1"><strong>นาย</strong></label>
                  </div>
                  <div class="form-check">
                    <input v-model="form.gender" type="radio" class="form-check-input" id="inlineRadio2"
                      name="type_print" value="นางสาว">
                    <label class="form-check-label" for="inlineRadio2"><strong>นางสาว</strong></label>
                  </div>
                </div>
                <div class="form-group mb-3">
                  <label for="my-input" class="mb-2">เลือกรหัสวิชา</label><br>
                  <button type="button" @click="form.passSubject = 30203" :class="{'active':form.passSubject == 30203}" class="btn btn-sm btn-outline-info">ว30203 (ภาคเรียนที่ 1)</button>
                  <button type="button" @click="form.passSubject = 30204" :class="{active:form.passSubject == 30204}" class="btn btn-sm btn-outline-info ml-2">ว30204 (ภาคเรียนที่ 2)</button>
                  
                </div>
              </div>
              <div class="row">
                <div class="col-md">
                  <div class="form-group">
                    <label for="">ชื่อ (<strong class="text-danger">ไม่มีคำนำหน้า</strong>)</label>
                    <input v-model="form.fname" type="text" class="form-control" placeholder="ตัวอย่าง : รักเรียน"
                      aria-describedby="helpId">
                  </div>
                </div>
                <div class="col-md">
                  <div class="form-group">
                    <label for="">นามสกุล</label>
                    <input v-model="form.lname" type="text" class="form-control" placeholder="ตัวอย่าง : ทำดี"
                      aria-describedby="helpId">
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md">
                  <div class="form-group">
                    <label for="">เลขที่</label>
                    <input v-model="form.number" type="number" class="form-control" placeholder="ตัวอย่าง : 16"
                      aria-describedby="helpId">
                  </div>
                </div>
                <div class="col-md">
                  <div class="form-group">
                    <label for="">ห้อง</label>
                    <input v-model="form.grade" type="number" class="form-control" placeholder="ตัวอย่าง : 10"
                      aria-describedby="helpId">
                  </div>
                </div>
              </div>
              <div class="form-group">
                <button @click="screenCap(form.fname)" class="btn btn-success"><i
                    class="fas fa-camera"></i>&nbsp;บันทึกเป็นภาพ</button>
              </div>
              <div class="form-group">

                <button @click="downValue()" class="btn btn-primary"><i class="fas fa-sort-size-down"></i>
                  ลดขนาด</button>
                <!-- <button class="btn btn-primary ml-2">{{font_size}}</button> -->
                <button @click="addValue()" class="btn btn-primary ml-2"><i class="fas fa-sort-size-up"></i>
                  เพิ่มขนาด</button>
                <button @click="upValueV()" class="btn btn-primary ml-2"><i class="fas fa-chevron-up"></i>
                  เลื่อนขึ้น</button>
                <button @click="downValueV()" class="btn btn-primary ml-2"><i class="fas fa-chevron-down"></i>
                  เลื่อนลง</button>
              </div>
              <div class="form-group">
                <button @click="resetCss()" class="btn btn-danger"><i class="fas fa-redo"></i> ค่าเริ่มต้น</button>
              </div>
              
            </div>
            <div class="card-footer">
              <div class="row">
                <div class="col-sm">
                  <center>Copyright © 2020 Generator NameTag For Physics</center>
                </div>
                <div class="col-sm">
                  <center> Website By Teerut Srithongdee 5/3</center>
                </div>
              </div>
              </div>
          </div>
      <div class="nametag_1 mt-1">
        <div class="nametag">
        <img src="./assets/template.png" alt="Snow">
        <h1 class="top-center" :style="'font-size:'+font_size+'vw; top: '+top+'%;'">
          <b>
            <p>
              <nobr>ชื่อ {{form.gender}} {{form.fname}}&nbsp;&nbsp;นามสกุล {{form.lname}}</nobr>
            </p>
            <p>
              <nobr class="">ชั้น ม.5/{{form.grade}} เลขที่ {{form.number}}</nobr>
            </p>
            <p>
              <nobr class="">วิชา ฟิสิกส์ ว{{form.passSubject}} สมุดจด</nobr>
            </p>
            <p>
              <nobr class="">ครูผู้สอน ธัญญารัตน์ โพธิ์ทอง</nobr>
            </p>
          </b>
        </h1>
      </div>
      <div class="nametag mt-1">
        <img src="./assets/template.png" alt="Snow">
        <h1 class="top-center" :style="'font-size:'+font_size+'vw; top: '+top+'%;'">
          <b>
            <p>
              <nobr>ชื่อ {{form.gender}} {{form.fname}}&nbsp;&nbsp;นามสกุล {{form.lname}}</nobr>
            </p>
            <p>
              <nobr class="">ชั้น ม.5/{{form.grade}} เลขที่ {{form.number}}</nobr>
            </p>
            <p>
              <nobr class="">วิชา ฟิสิกส์ ว{{form.passSubject}} สมุดแบบฝึกหัด</nobr>
            </p>
            <p>
              <nobr class="">ครูผู้สอน ธัญญารัตน์ โพธิ์ทอง</nobr>
            </p>
          </b>
        </h1>
      </div>
      </div>
    </div>
  </div>
</template>

<script>
  const html2canvas = require('html2canvas');
  export default {
    name: 'App',
    components: {},
    data() {
      return {
        form: {
          gender: "นาย",
          fname: "",
          lname: "",
          number: "",
          grade: 0,
          passSubject: 30203,
        },
        font_size: 3,
        top: 50
      }
    },
    methods: {
      addValue() {
        this.font_size = this.font_size + 0.3
      },
      downValue() {
        this.font_size = this.font_size - 0.3
      },
      upValueV() {
        this.top = this.top - 1
      },
      downValueV() {
        this.top = this.top + 1
      },
      resetCss() {
        this.top = 55
        this.font_size = 3.0
      },
      screenCap: function (name) {
        // setTimeout(() => {
        //   var offScreen = document.querySelector('.nametag_1');
        //   window.scrollTo(0, 0);
        //   // var clone = hiddenClone(offScreen);
        //   // Use clone with htm2canvas and delete clone
        //   html2canvas(offScreen, {
        //     scrollY: -window.scrollY
        //   }).then((canvas) => {

        //     var dataURL = canvas.toDataURL("image/png", 1.0);
        //     // document.body.removeChild(clone);
        //     var link = document.createElement('a');
        //     link.download = 'สมุดจด_' + name + '.png';
        //     link.href = dataURL;
        //     this.imgDataUrl = dataURL;
        //     document.body.appendChild(link);
        //     link.click();
        //     document.body.removeChild(link);
        //   });
        // }, 1000)
        var offScreen = document.querySelector('.nametag_1');
        window.scrollTo(0, 0);
        // var clone = hiddenClone(offScreen);
        // Use clone with htm2canvas and delete clone
        html2canvas(offScreen, {
          scrollY: -window.scrollY
        }).then((canvas) => {

          var dataURL = canvas.toDataURL("image/png", 1.0);
          // document.body.removeChild(clone);
          var link = document.createElement('a');
          link.href = dataURL;
          link.download = 'สมุดแบบฝึกหัด_' + name + '.png';
          this.imgDataUrl = dataURL;
          document.body.appendChild(link);
          link.click();
          document.body.removeChild(link);
        });

      },
    }
  }
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Kanit&display=swap');
  @font-face {
    font-family: 'THSarabunNew';
    src: url('./assets/font/THSarabunNew.ttf');
    font-weight: normal;
    font-style: normal;

  }
  body{
    font-family: 'Kanit', sans-serif;
  }

  /* Container holding the image and the text */
  .nametag {
    font-family: 'THSarabunNew', sans-serif;
    position: relative;
    text-align: center;
    border: 1px solid #000000;
  }

  /* Top right text */
  .top-center {
    position: absolute;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  img {
    width: 100%;
    height: auto;
  }

  nobr {
    margin-top: 100px;
  }
</style>