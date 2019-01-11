<template>
  <div class="app-container">
    <div class="w">
      <h1>政府信息公开申请表</h1>
      <div class="zhu">
        注：公民、法人选择其一填写即可；
        <span class="red">*</span> 为必填项。
      </div>
      <!-- table -->
      <form action="http://www.hd.gov.cn/infogate/CustomInfoViewDataAdapt" method="post">
        <table cellpadding="0" cellspacing="0" border="1">
          <tr>
            <td rowspan="14" style="width:30px;background-color:#ffeeee;font-size: 18px;">申请人信息</td>
            <td
              rowspan="7"
              style="width:110px;background-color:#f6f6f6;cursor: pointer;"
              @click="gm"
              class="gongmin"
            >公民</td>
            <td class="huibg">
              <span class="red">*</span>姓名
            </td>
            <td>
              <input type="text" name="username" v-model="username" class="gm_table">
            </td>
            <td class="huibg">
              <span class="red">*</span>工作单位
            </td>
            <td>
              <input type="text" name="danwei" v-model="danwei" class="gm_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">
              <span class="red">*</span>证件名称
            </td>
            <td>
              <input type="text" name="zhengjianname" v-model="zhengjianname" class="gm_table">
            </td>
            <td class="huibg">
              <span class="red">*</span>证件号码
            </td>
            <td>
              <input type="text" name="zhengjiannum" v-model="zhengjiannum" class="gm_table">
            </td>
          </tr>
          <tr>
            <td rowspan="2" class="huibg">
              <span class="red">*</span>证件扫描或照片
            </td>
            <td colspan="3" class="t_a_l">
              <input
                type="text"
                name="gmzj1"
                ref="gmzj1"
                placeholder="点击上传附件"
                style="cursor:pointer; width:260px;"
                readonly
                onclick="upload(this);"
                class="gm_table"
              >
              <span class="red">*</span>（证件正面，文件小于500K）
            </td>
          </tr>
          <tr>
            <td colspan="3" class="t_a_l">
              <input
                type="text"
                name="gmzj2"
                ref="gmzj2"
                placeholder="点击上传附件"
                style="cursor:pointer; width:260px;"
                readonly
                onclick="upload(this);"
                class="gm_table"
              >
              <span class="red">*</span>（证件背面，文件小于500K）
            </td>
          </tr>
          <tr>
            <td class="huibg">
              <span class="red">*</span>联系电话
            </td>
            <td>
              <input type="text" name="lxdianhua" v-model="lxdianhua" class="gm_table">
            </td>
            <td class="huibg">
              <span class="red">*</span>邮政编码
            </td>
            <td>
              <input type="text" name="yzbianma" v-model="yzbianma" class="gm_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">
              <span class="red">*</span>联系地址
            </td>
            <td colspan="3">
              <input type="text" name="lxdizhi" v-model="lxdizhi" class="gm_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">电子邮箱</td>
            <td colspan="3">
              <input type="text" name="email" v-model="email" class="gm_table">
            </td>
          </tr>
          <tr>
            <td
              rowspan="6"
              style="background-color:#ffffff;cursor: pointer;"
              @click="fr"
              class="faren"
            >法人/其它组织</td>
            <td class="huibg">
              <span class="red">*</span>名称
            </td>
            <td>
              <input type="text" name="frname" v-model="frname" class="fr_table">
            </td>
            <td class="huibg">
              <span class="red">*</span>统一社会信用代码
            </td>
            <td>
              <input type="text" name="xydaima" v-model="xydaima" class="fr_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">
              <span class="red">*</span>法人代表
            </td>
            <td>
              <input type="text" name="frdaibiao" v-model="frdaibiao" class="fr_table">
            </td>
            <td class="huibg">
              <span class="red">*</span>联系人姓名
            </td>
            <td>
              <input type="text" name="lxrname" v-model="lxrname" class="fr_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">
              <span class="red">*</span>法人证明扫描件或照片
            </td>
            <td colspan="3" class="t_a_l">
              <input
                type="text"
                name="frzj"
                ref="frzj"
                placeholder="点击上传附件"
                style="cursor:pointer; width:290px;"
                readonly
                onclick="upload(this);"
                class="fr_table"
              >
              <span class="red">*</span>（文件小于500K）
            </td>
          </tr>
          <tr>
            <td class="huibg">
              <span class="red">*</span>联系人电话
            </td>
            <td>
              <input type="text" name="lxrdianhua" v-model="lxrdianhua" class="fr_table">
            </td>
            <td class="huibg">
              <span class="red">*</span>邮政编码
            </td>
            <td>
              <input type="text" name="fryzbianma" v-model="fryzbianma" class="fr_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">
              <span class="red">*</span>联系地址
            </td>
            <td colspan="3">
              <input type="text" name="frlxdizhi" v-model="frlxdizhi" class="fr_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">电子邮箱</td>
            <td colspan="3">
              <input type="text" name="email1" v-model="email1" class="fr_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">申请时间</td>
            <td colspan="4">
              <input type="text" name="sqtime" disabled v-model="currentTime">
            </td>
          </tr>
          <tr>
            <td rowspan="6" style="background-color:#ffeeee;font-size: 18px;">所需信息情况</td>
            <td class="huibg">政府信息公开义务机关(机构)名称</td>
            <td colspan="4">
              <input type="text" name="jgname" v-model="jgname">
            </td>
          </tr>
          <tr>
            <td class="huibg">
              <span class="red">*</span>所需信息的内容描述（名称、文号或其他特征描述）
            </td>
            <td colspan="4">
              <textarea name="content" v-model="content" cols="30" rows="10"></textarea>
            </td>
          </tr>
          <tr>
            <td class="huibg">获取政府信息的方式</td>
            <td colspan="4" class="t_a_l">
              <input type="radio" name="fangshi" v-model="fangshi" value="1">邮寄
              <input type="radio" name="fangshi" v-model="fangshi" value="2">当面领取
              <input type="radio" name="fangshi" v-model="fangshi" value="3">现场查阅
            </td>
          </tr>
          <tr>
            <td class="huibg">政府信息的载体形式</td>
            <td colspan="4" class="t_a_l">
              <input type="radio" name="xingshi" v-model="xingshi" value="1">纸质文本
              <input type="radio" name="xingshi" v-model="xingshi" value="2">数据电文
            </td>
          </tr>
          <tr>
            <td rowspan="2" class="huibg">所需政府信息的用途</td>
            <td colspan="4" class="t_a_l">
              类型：
              <br>
              <input type="checkbox" name="yongtu" v-model="yongtu" value="true">自身生产的需要
              <input type="checkbox" name="yongtu1" v-model="yongtu1" value="true">自身生活的需要
              <input type="checkbox" name="yongtu2" v-model="yongtu2" value="true">自身科研的需要
              <input type="checkbox" name="yongtu3" v-model="yongtu3" value="true">查验自身信息
            </td>
          </tr>
          <tr>
            <td colspan="4">
              <textarea name="content1" v-model="content1" cols="30" rows="10"></textarea>
            </td>
          </tr>
        </table>
        <div class="tj_cz">
          <input name="FileFieldName" value="gmzj1,gmzj2,frzj" type="hidden">
          <input value="0" name="needverifycode" type="hidden">
          <input value="166" name="SiteId" type="hidden">
          <input value="27730" name="ChannelId" type="hidden">
          <input value="35" name="InfoViewId" type="hidden">
          
          <input type="submit" value="提交" @click="tijiao">
          <input type="reset" value="重置" @click="reset">
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentTime: new Date().format("yyyy年mm月dd日"),
      gmflag: true,
      frflag: true,

      username: "",
      danwei: "",
      zhengjianname: "",
      zhengjiannum: "",
      gmzj1: "",
      gmzj2: "",
      lxdianhua: "",
      yzbianma: "",
      lxdizhi: "",
      email: "",
      frname: "",
      xydaima: "",
      frdaibiao: "",
      lxrname: "",
      frzj: "",
      lxrdianhua: "",
      fryzbianma: "",
      frlxdizhi: "",
      email1: "",
      jgname: "",
      content: "",
      fangshi: "",
      fangshi: "",
      fangshi: "",
      xingshi: "",
      xingshi: "",
      yongtu: "",
      yongtu1: "",
      yongtu2: "",
      yongtu3: "",
      content1: ""
    };
  },
  methods: {
    gm() {
      this.gmflag = true;
      this.frflag = false;
      document.querySelector(".gongmin").style.backgroundColor = "#f6f6f6";
      document.querySelector(".faren").style.backgroundColor = "#ffffff";
      var gm_tables = document.querySelectorAll(".gm_table");
      for (var i = 0; i < gm_tables.length; i++) {
        gm_tables[i].disabled = "";
      }
      var fr_tables = document.querySelectorAll(".fr_table");
      for (var i = 0; i < fr_tables.length; i++) {
        fr_tables[i].disabled = "disabled";
        fr_tables[i].value = "";
      }
      this.frname = "";
      this.xydaima = "";
      this.frdaibiao = "";
      this.lxrname = "";
      this.lxrdianhua = "";
      this.fryzbianma = "";
      this.frlxdizhi = "";
      this.email1 = "";
    },
    fr() {
      this.gmflag = false;
      this.frflag = true;
      document.querySelector(".gongmin").style.backgroundColor = "#ffffff";
      document.querySelector(".faren").style.backgroundColor = "#f6f6f6";
      var gm_tables = document.querySelectorAll(".gm_table");
      for (var i = 0; i < gm_tables.length; i++) {
        gm_tables[i].disabled = "disabled";
        gm_tables[i].value = "";
      }
      var fr_tables = document.querySelectorAll(".fr_table");
      for (var i = 0; i < fr_tables.length; i++) {
        fr_tables[i].disabled = "";
      }
      this.username = "";
      this.danwei = "";
      this.zhengjianname = "";
      this.zhengjiannum = "";
      this.lxdianhua = "";
      this.yzbianma = "";
      this.lxdizhi = "";
      this.email = "";
    },
    tijiao(event) {
      if (this.gmflag) {
        if (
          this.$refs.gmzj1.value != "" &&
          this.$refs.gmzj2.value != "" &&
          this.username &&
          this.danwei &&
          this.zhengjianname &&
          this.zhengjiannum &&
          this.lxdianhua &&
          this.yzbianma &&
          this.lxdizhi &&
          this.content
        ) {
        } else {
          event.preventDefault();
          alert("请填写完整信息");
        }
      } else if (this.frflag) {
        if (
          this.$refs.frzj.value != "" &&
          this.frname &&
          this.xydaima &&
          this.frdaibiao &&
          this.lxrname &&
          this.lxrdianhua &&
          this.fryzbianma &&
          this.frlxdizhi &&
          this.content
        ) {
        } else {
          event.preventDefault();
          alert("请填写完整信息");
        }
      }
    },
    reset() {
      this.username = "";
      this.danwei = "";
      this.zhengjianname = "";
      this.zhengjiannum = "";
      this.gmzj1 = "";
      this.gmzj2 = "";
      this.lxdianhua = "";
      this.yzbianma = "";
      this.lxdizhi = "";
      this.email = "";
      this.frname = "";
      this.xydaima = "";
      this.frdaibiao = "";
      this.lxrname = "";
      this.frzj = "";
      this.lxrdianhua = "";
      this.fryzbianma = "";
      this.frlxdizhi = "";
      this.email1 = "";
      this.jgname = "";
      this.content = "";
      this.fangshi = "";
      this.fangshi = "";
      this.fangshi = "";
      this.xingshi = "";
      this.xingshi = "";
      this.yongtu = "";
      this.yongtu1 = "";
      this.yongtu2 = "";
      this.yongtu3 = "";
      this.content1 = "";
    }
  },
  created() {},
  mounted() {
    this.gm();
  }
};
</script>

<style lang="scss" scoped>
.red {
  color: #f00;
}

.huibg {
  background-color: #f6f6f6;
}

.app-container {
  color: #000;
  font-size: 14px;
  font-family: "Microsoft YaHei";
}
.app-container .w {
  width: 1200px;
  margin: 0 auto;
}
.app-container h1 {
  text-align: center;
  font-size: 30px;
  line-height: 60px;
  font-weight: bold;
  margin: 0;
}
.app-container .zhu {
  text-align: center;
}
.app-container table {
  width: 80%;
  margin: 25px auto;
}
.app-container table td {
  text-align: center;
  line-height: 36px;
}
.app-container table td.t_a_l {
  text-align: left;
}
.app-container table input {
  width: 100%;
  height: 34px;
  vertical-align: top;
  font-size: 14px;
  color: #000;
  border: none;
}
.app-container table input[type="radio"] {
  display: inline-block;
  width: auto;
  margin-left: 10px;
}
.app-container table input[type="checkbox"] {
  display: inline-block;
  width: auto;
  margin-left: 10px;
}
.app-container table textarea {
  width: 98%;
  border: none;
}
.app-container .tj_cz {
  text-align: center;
  margin-bottom: 25px;
}
.app-container .tj_cz [type="submit"] {
  display: inline-block;
  width: 100px;
  height: 32px;
  font-size: 20x;
  line-height: 32px;
  color: #000;
  text-align: center;
  margin: 0 10px;
}
.app-container .tj_cz [type="reset"] {
  display: inline-block;
  width: 100px;
  height: 32px;
  font-size: 20x;
  line-height: 32px;
  color: #000;
  text-align: center;
  margin: 0 10px;
}
</style>