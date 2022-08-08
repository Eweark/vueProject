<template>
	<div id="pageBody">
		<el-row :gutter="20">
			<el-col :span="6">
				<div class="grid-content bg-purple">
					<div class="img">
						<img src="../assets/commodity/a.png" width="300px" height="180px" />
					</div>
					 </div>
			</el-col>
			<el-col :span="6">
				<div class="grid-content bg-purple">
					<div class="img">
						<img src="../assets/commodity/b.png"  width="300px" height="180px"/>
					</div>
					 </div>
			</el-col>
			<el-col :span="6">
				<div class="grid-content bg-purple">
					<div class="img">
						<img src="../assets/commodity/c.png" width="300px" height="180px">
					</div>
					
					</div>
			</el-col>
			<el-col :span="6">
				<div class="grid-content bg-purple">
					<div class="img">
						<img src="../assets/commodity/b.png" width="300px" height="180px" />
					</div>
					 </div>
			</el-col>
		</el-row>
		<img src="../assets/img/im.png" width="1270px" />
		<div id="com">
			<h2>手机</h2>
			<el-row>
			  <el-col :span="4"><div class="grid-content bg-purple">
			  <img src="../assets/commodity/u.png" height="580px" />
			  </div></el-col>
			  <el-col :span="20" style="margin-top: -15px;"><div class="grid-content bg-purple-light">
			  <ul>
			  		<el-row>
			  		  <el-col :span="5"  v-for="comm in commodityData" :key="comm.id"  style="margin-left: 20px;margin-top: 10px;">
			  		    <el-card :body-style="{ padding: '0px' }" shadow="hover">
			  		      <img :src="comm.url" class="image">
			  		      <div style="padding: 14px;">
			  		        <span>{{comm.name}}</span><br />
							<span style="color: #ff6700;">{{comm.price}}</span>
			  		      </div>
			  		    </el-card>
			  		  </el-col>
			  		</el-row>
			  	
			  </ul></div></el-col>
			</el-row>
			
			
			
			
		</div>
		
	</div>
</template>

<script>
	export default {
		name: 'pageBody',
		data() {
			return {
				commodityData: [
					{id:'1',url :require('../assets/commodity/xiaomi12.png'),name:'小米12',price:'9999'},
					{id:'2',url :require('../assets/commodity/xiaomi12s.png'),name:'小米12s'},
					{id:'3',url :require('../assets/commodity/xiaomi12su.png'),name:'小米12s Uitra'},
					{id:'4',url :require('../assets/commodity/1.png'),name:'小米12Pro 天玑版'},
					{id:'5',url :require('../assets/commodity/note11t.png'),name:'Redmi Note 11T pro+'},
					{id:'6',url :require('../assets/commodity/note11pt.png'),name:'Redmi Note 11T pro'},
					{id:'7',url :require('../assets/commodity/red.png'),name:'Redmi Note 11T SE'},
					{id:'8',url :require('../assets/commodity/civi9.png'),name:'xiaomi Civi1S'}
				]
			}
		}
	}
</script>

<style>
	.img{
		margin-left: ;
	}
	.el-row {
		margin-bottom: 20px;

		&:last-child {
			margin-bottom: 0;
		}
	}
	/* {
		background-color: #f5f5f5;
	} */

	.el-col {
		border-radius: 4px;
	}

	.bg-purple-dark {
		/* background: #99a9bf; */
	}

	.bg-purple {
		/* background: #d3dce6; */
	}

	.bg-purple-light {
		/* background: #e5e9f2; */
	}

	.grid-content {
		border-radius: 4px;
		min-height: 36px;
	}

	.row-bg {
		padding: 10px 0;
		/* background-color: #f9fafc; */
	}

	.time {
		font-size: 13px;
		color: #999;
	}

	.bottom {
		margin-top: 13px;
		line-height: 12px;
	}

	.button {
		padding: 0;
		float: right;
	}

	.image {
		width: 100%;
		display: block;
	}

	.clearfix:before,
	.clearfix:after {
		display: table;
		content: "";
	}

	.clearfix:after {
		clear: both
	}
</style>
