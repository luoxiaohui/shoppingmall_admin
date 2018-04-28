<template>
  <div class="app-container">
    <el-form ref="form" :model="commodity" label-width="120px">
      <el-form-item label="商品名">
        <el-input v-model="commodity.commodityName" style="width:360px"></el-input>
      </el-form-item>
      <el-form-item label="商品类型">
        <el-select v-model="commodity.commodityType" placeholder="未选择">
          <el-option label="服饰服装" value="01"></el-option>
          <el-option label="日用百货" value="02"></el-option>
          <el-option label="鞋帽箱包" value="03"></el-option>
          <el-option label="文体用品" value="04"></el-option>
          <el-option label="化妆品" value="05"></el-option>
          <el-option label="电子产品" value="06"></el-option>
          <el-option label="家纺" value="07"></el-option>
          <el-option label="家居用品" value="08"></el-option>
          <el-option label="皮草" value="09"></el-option>
          <el-option label="玩具" value="10"></el-option>
          <el-option label="五金厨具" value="11"></el-option>
          <el-option label="计算机软件及辅助设备的销售" value="12"></el-option>
          <el-option label="计算机软件开发" value="13"></el-option>
          <el-option label="计算机系统集成" value="14"></el-option>
        </el-select>
      </el-form-item>
      <el-form-item label="商品价格">
        <el-input v-model="commodity.commodityPrice" style="width:120px"></el-input>
      </el-form-item>
      <el-form-item label="商品具体参数">
        <el-input v-model="commodity.commodityDetailParams" style="width:240px"></el-input>
      </el-form-item>
      <el-form-item label="商品缩略图">
        <el-button @click="addThumbnail">添加</el-button>
      </el-form-item>
       <!-- <div class="upload">
        <div class="upload_warp">
          <div class="upload_warp_left" @click="fileClick">
            <img src="./upload.png">
          </div>
          <div class="upload_warp_right" @drop="drop($event)" @dragenter="dragenter($event)" @dragover="dragover($event)">
            或者将文件拖到此处
          </div>
        </div>
        <div class="upload_warp_text">
          选中{{imgList.length}}张文件，共{{bytesToSize(this.size)}}
        </div>
        <input @change="fileChange($event)" type="file" id="upload_file" multiple style="display: none"/>
        <div class="upload_warp_img" v-show="imgList.length!=0">
          <div class="upload_warp_img_div" v-for="(item,index) of imgList">
            <div class="upload_warp_img_div_top">
              <div class="upload_warp_img_div_text">
                {{item.file.name}}
              </div>
              <img src="./del.png" class="upload_warp_img_div_del" @click="fileDel(index)">
            </div>
            <img :src="item.file.src">
          </div>
        </div>
      </div> -->
      <el-form-item label="商品详情">
        <el-input v-model="commodity.commodityDetail" style="width:240px" placeholder="用html或图片，暂定"></el-input>
      </el-form-item>
     
      <!-- <el-form-item label="Activity form">
        <el-input type="textarea" v-model="form.desc"></el-input>
      </el-form-item> -->
      <el-form-item>
        <el-button type="primary" @click="onSubmit">添加</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      commodity: {
        commodityName: '',
        commodityType: '',
        commodityPrice: '',
        commodityDetailParams: '',
        commodityDetail: ''
      }
    }
  },
  methods: {
    onSubmit() {
      this.$message('submit!')
    },
    addThumbnail() {
      this.$message('添加缩略图')
    }
  }
}
</script>

<style scoped>
.line{
  text-align: center;
}
</style>

