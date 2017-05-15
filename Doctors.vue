<template>
  <div class="Doctor">
       <div class="list">
          <h3>
            <span class="list-blue"></span>
            <span class="list-doctor">{{ title }}</span>
          </h3>
        </div>
        <div class="list-all">
            <div class="list-con" v-for="doctor in doctors">
                <dl>
                  <dt><router-link to="/disc"><img  v-bind:src="doctor.image_url" /></router-link></dt>
                  <dd class="name">{{doctor.name}} <span class="director">{{doctor.honor}}</span></dd>
                  <dd class="hospital">{{doctor.hosptial}}</dd>
                  <dd class="part">{{doctor.part}}</dd>
                </dl>
                <ul>
                 <li><span>1</span>{{sickManage}}</li>
                 <li><span>2</span>{{serveManage}}</li>
                 <li><span>3</span>{{orderManage}}</li>
                </ul>
            </div> 
        </div>
  </div>
</template>
<script>

export default {
  name: 'Doctor',
  data () {
    let doctors = []  
     let doctor = { 'name':'宋小宝', 'honor': '主任医师', 'hosptial': '北京协和医院', 'part': '神经内科' ,image_url:"static/22.jpg"}
    doctors.push(doctor)
    doctors.push(doctor)     
    doctors.push(doctor)
     doctors.push(doctor)     
    let page = {}
    page.doctors = doctors
    page.title = '医生列表'
    page.sickManage='患者管理'
    page.serveManage='服务设置'
    page.orderManage='订单管理'
    return page
  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.Doctor{
  width:100%;margin:0px auto; background:white; margin-top:20px;
}
.list{width:100%; border-bottom:1px solid #ccc;}
h3{display:block; width:100%; height:100px; font-weight: normal; line-height:50px; text-align:left;position:relative; }
h3 span.list-blue{ display:block; width:5px; height:50px; background:blue; position:absolute;top:30px; left:80px;}
h3 span.list-doctor { width:200px; display:block; position:absolute; top:30px; left:100px; font-size:40px;}
.list-con{ width:100%; background:white;}
.list-con dl{ width:100%;  margin:20px auto;}
.list-con dl dt{width:30%;height:150px;float:left;padding-top:10px; padding-top:60px;}
.list-con dl dd{width:68%;float:right;font-size:30px; color:#666;  text-align:left; line-height:60px;}
.list-con dl dd.name{font-size:36px; }
.list-con dl dd.name span{font-size:30px;color:blue;}
.list-con dl dd.hospital{font-size:34px;}
.list-con dl dd.part{font-size:30px;color:#aaa; border-bottom:1px solid #ccc;}
.list-con ul{ clear:both; width:100%; height:50px;padding-top:30px;padding-bottom:30px;border-bottom:1px solid #ccc;}
.list-con ul li{float:left;font-size:36px; padding-left:120px;}
*{ padding:0px; margin:0px; }
</style>
