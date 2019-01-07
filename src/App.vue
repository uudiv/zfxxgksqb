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
              <input type="text" name="username" class="gm_table">
            </td>
            <td class="huibg">
              <span class="red">*</span>工作单位
            </td>
            <td>
              <input type="text" name="danwei" class="gm_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">
              <span class="red">*</span>证件名称
            </td>
            <td>
              <input type="text" name="zhengjianname" class="gm_table">
            </td>
            <td class="huibg">
              <span class="red">*</span>证件号码
            </td>
            <td>
              <input type="text" name="zhengjiannum" class="gm_table">
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
              <input type="text" name="lxdianhua" class="gm_table">
            </td>
            <td class="huibg">
              <span class="red">*</span>邮政编码
            </td>
            <td>
              <input type="text" name="yzbianma" class="gm_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">
              <span class="red">*</span>联系地址
            </td>
            <td colspan="3">
              <input type="text" name="lxdizhi" class="gm_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">电子邮箱</td>
            <td colspan="3">
              <input type="text" name="email" class="gm_table">
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
              <input type="text" name="frname" class="fr_table">
            </td>
            <td class="huibg">
              <span class="red">*</span>统一社会信用代码
            </td>
            <td>
              <input type="text" name="xydaima" class="fr_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">
              <span class="red">*</span>法人代表
            </td>
            <td>
              <input type="text" name="frdaibiao" class="fr_table">
            </td>
            <td class="huibg">
              <span class="red">*</span>联系人姓名
            </td>
            <td>
              <input type="text" name="lxrname" class="fr_table">
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
              <input type="text" name="lxrdianhua" class="fr_table">
            </td>
            <td class="huibg">
              <span class="red">*</span>邮政编码
            </td>
            <td>
              <input type="text" name="fryzbianma" class="fr_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">
              <span class="red">*</span>联系地址
            </td>
            <td colspan="3">
              <input type="text" name="frlxdizhi" class="fr_table">
            </td>
          </tr>
          <tr>
            <td class="huibg">电子邮箱</td>
            <td colspan="3">
              <input type="text" name="email1" class="fr_table">
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
              <input type="text" name="jgname">
            </td>
          </tr>
          <tr>
            <td class="huibg">
              <span class="red">*</span>所需信息的内容描述（名称、文号或其他特征描述）
            </td>
            <td colspan="4">
              <textarea name="content" cols="30" rows="10"></textarea>
            </td>
          </tr>
          <tr>
            <td class="huibg">获取政府信息的方式</td>
            <td colspan="4" class="t_a_l">
              <input type="radio" name="fangshi" value="1">邮寄
              <input type="radio" name="fangshi" value="2">当面领取
              <input type="radio" name="fangshi" value="3">现场查阅
            </td>
          </tr>
          <tr>
            <td class="huibg">政府信息的载体形式</td>
            <td colspan="4" class="t_a_l">
              <input type="radio" name="xingshi" value="1">纸质文本
              <input type="radio" name="xingshi" value="2">数据电文
            </td>
          </tr>
          <tr>
            <td rowspan="2" class="huibg">所需政府信息的用途</td>
            <td colspan="4" class="t_a_l">
              类型：
              <br>
              <input type="checkbox" name="yongtu" value="true">自身生产的需要
              <input type="checkbox" name="yongtu1" value="true">自身生活的需要
              <input type="checkbox" name="yongtu2" value="true">自身科研的需要
              <input type="checkbox" name="yongtu3" value="true">查验自身信息
            </td>
          </tr>
          <tr>
            <td colspan="4">
              <textarea name="content1" cols="30" rows="10"></textarea>
            </td>
          </tr>
        </table>
        <div class="tj_cz">
          <input name="FileFieldName" value="gmzj1,gmzj2,frzj" type="hidden">
          <input value="0" name="needverifycode" type="hidden">
          <input value="166" name="SiteId" type="hidden">
          <input value="27730" name="ChannelId" type="hidden">
          <input value="35" name="InfoViewId" type="hidden">
          
          <input type="submit" value="提交" @click.stop.prevent="tijiao">
          <input type="reset" value="重置">
        </div>
      </form>
    </div>
  </div>
</template>

<script>
var $ = require("jquery");

export default {
  data() {
    return {
      currentTime: new Date().format("yyyy年mm月dd日")
    };
  },
  methods: {
    gm() {
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
    },
    fr() {
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
    },
    tijiao() {
      var data = $("form").serializeArray();
      for (var i = 0; i < data.length; i++) {
        if (data[i].value == "") {
          alert("请填写完整");
          return false;
        }
      }
      alert("ok");
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
  .w {
    width: 1200px;
    margin: 0 auto;
  }
  h1 {
    text-align: center;
    font-size: 30px;
    line-height: 60px;
    font-weight: bold;
    margin: 0;
  }
  .zhu {
    text-align: center;
  }
  table {
    width: 80%;
    margin: 25px auto;
    td {
      text-align: center;
      line-height: 36px;
      &.t_a_l {
        text-align: left;
      }
    }
    input {
      width: 100%;
      height: 34px;
      vertical-align: top;
      font-size: 14px;
      color: #000;
      border: none;
      &[type="radio"] {
        display: inline-block;
        width: auto;
        margin-left: 10px;
      }
      &[type="checkbox"] {
        display: inline-block;
        width: auto;
        margin-left: 10px;
      }
    }
    textarea {
      width: 98%;
      border: none;
    }
  }
  .tj_cz {
    text-align: center;
    margin-bottom: 25px;

    [type="submit"] {
      display: inline-block;
      width: 100px;
      height: 32px;
      font-size: 20x;
      line-height: 32px;
      color: #000;
      text-align: center;
      margin: 0 10px;
    }
    [type="reset"] {
      display: inline-block;
      width: 100px;
      height: 32px;
      font-size: 20x;
      line-height: 32px;
      color: #000;
      text-align: center;
      margin: 0 10px;
    }
  }
}
</style>


