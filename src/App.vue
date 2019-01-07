<template>
  <div class="app-container">
    <div class="w">
      <h1>政府信息公开申请表</h1>
      <br>
      <div class="zhu">
        注：公民、法人选择其一填写即可；
        <span class="red">*</span> 为必填项。
      </div>
      <!-- table -->
      <form action="http://www.hd.gov.cn/infogate/CustomInfoViewDataAdapt" method="post">
        <table cellpadding="0" cellspacing="0" border="1">
          <tr>
            <td rowspan="14" style="width:30px;background-color:#ffeeee;font-size: 18px;">申请人信息</td>
            <td rowspan="7" style="width:200px;">公民</td>
            <td>姓名</td>
            <td>
              <input type="text" name="username">
            </td>
            <td>工作单位</td>
            <td>
              <input type="text" name="danwei">
            </td>
          </tr>
          <tr>
            <td>证件名称</td>
            <td>
              <input type="text" name="zhengjianname">
            </td>
            <td>证件号码</td>
            <td>
              <input type="text" name="zhengjiannum">
            </td>
          </tr>
          <tr>
            <td rowspan="2">证件扫描或照片</td>
            <td colspan="3">
              <input type="file" name id>（证件正面，文件小于500K）
            </td>
          </tr>
          <tr>
            <td colspan="3">
              <input type="file" name id>（证件背面，文件小于500K）
            </td>
          </tr>
          <tr>
            <td>联系电话</td>
            <td>
              <input type="text" name>
            </td>
            <td>邮政编码</td>
            <td>
              <input type="text" name>
            </td>
          </tr>
          <tr>
            <td>联系地址</td>
            <td colspan="3">
              <input type="text" name>
            </td>
          </tr>
          <tr>
            <td>电子邮箱</td>
            <td colspan="3">
              <input type="text" name>
            </td>
          </tr>
          <tr>
            <td rowspan="6">法人/其它组织</td>
            <td>名称</td>
            <td>
              <input type="text" name>
            </td>
            <td>统一社会信用代码</td>
            <td>
              <input type="text" name>
            </td>
          </tr>
          <tr>
            <td>法人代表</td>
            <td>
              <input type="text" name>
            </td>
            <td>联系人姓名</td>
            <td>
              <input type="text" name>
            </td>
          </tr>
          <tr>
            <td>法人证明扫描件或照片</td>
            <td colspan="3">
              <input type="file" name id>（文件小于500K）
            </td>
          </tr>
          <tr>
            <td>联系人电话</td>
            <td>
              <input type="text" name>
            </td>
            <td>邮政编码</td>
            <td>
              <input type="text" name>
            </td>
          </tr>
          <tr>
            <td>联系地址</td>
            <td colspan="3">
              <input type="text" name>
            </td>
          </tr>
          <tr>
            <td>电子邮箱</td>
            <td colspan="3">
              <input type="text" name>
            </td>
          </tr>
          <tr>
            <td>申请时间</td>
            <td colspan="4">
              <input type="text" name>
            </td>
          </tr>
          <tr>
            <td rowspan="6" style="background-color:#ffeeee;font-size: 18px;">所需信息情况</td>
            <td>政府信息公开义务机关(机构)名称</td>
            <td colspan="4">
              <input type="text" name>
            </td>
          </tr>
          <tr>
            <td>所需信息的内容描述（名称、文号或其他特征描述）</td>
            <td colspan="4">
              <textarea name id cols="30" rows="10"></textarea>
            </td>
          </tr>
          <tr>
            <td>获取政府信息的方式</td>
            <td colspan="4" class="t_a_l">
              <input type="radio" name id>邮寄
              <input type="radio" name id>当面领取
              <input type="radio" name id>现场查阅
            </td>
          </tr>
          <tr>
            <td>政府信息的载体形式</td>
            <td colspan="4" class="t_a_l">
              <input type="radio" name id>纸质文本
              <input type="radio" name id>数据电文
            </td>
          </tr>
          <tr>
            <td rowspan="2">所需政府信息的用途</td>
            <td colspan="4" class="t_a_l">
              类型：
              <br>
              <input type="checkbox" value="自身生产的需要">自身生产的需要
              <input type="checkbox" value="自身生活的需要">自身生活的需要
              <input type="checkbox" value="自身科研的需要">自身科研的需要
              <input type="checkbox" value="查验自身信息">查验自身信息
            </td>
          </tr>
          <tr>
            <td colspan="4">
              <textarea name id cols="30" rows="10"></textarea>
            </td>
          </tr>
        </table>
        <div class="tj_cz">
          <input value="0" name="needverifycode" type="hidden">
          <input value="166" name="SiteId" type="hidden">
          <input value="27730" name="ChannelId" type="hidden">
          <input value="35" name="InfoViewId" type="hidden">
          
          <input type="submit" value="提交">
          <input type="reset" value="重置">
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {},
  created() {

  }
};
</script>

<style lang="scss" scoped>
.red {
  color: #f00;
}
.app-container {
  color: #000;
  font-size: 16px;
  font-family: "Microsoft YaHei";
  .w {
    width: 1200px;
    margin: 0 auto;
  }
  h1 {
    text-align: center;
    font-size: 30px;
    font-weight: bold;
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
      width: 98%;
      height: 34px;
      vertical-align: top;
      font-size: 16px;
      color: #000;
      border: none;
      &[type="radio"] {
        display: inline-block;
        width: auto;
      }
      &[type="checkbox"] {
        display: inline-block;
        width: auto;
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


