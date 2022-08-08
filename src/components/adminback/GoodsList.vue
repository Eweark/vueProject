<template>
	<div>
		 <el-table
		     :data="tableData.filter(data => !search || data.sname.toLowerCase().includes(search.toLowerCase()))"
		     style="width: 100%" :row-class-name="tableRowClassName">
		     <el-table-column
		       label="商品id"
		       prop="id">
		     </el-table-column>
		     <el-table-column
		       label="商品名称"
		       prop="sname">
		     </el-table-column>
			 <el-table-column
			   label="商品价格"
			   prop="sprice">
			 </el-table-column>
			 <el-table-column
			   label="商品数量"
			   prop="snum">
			 </el-table-column>
			 <el-table-column
			   label="商品图片"
			   prop="img">
			 </el-table-column>
			 <el-table-column
			   label="商品属性"
			   prop="desc">
			 </el-table-column>
		     <el-table-column
		       align="right">
		       <template slot="header" slot-scope="scope">
		         <el-input
		           v-model="search"
		           size="mini"
		           placeholder="输入关键字搜索"/>
		       </template>
		       <template slot-scope="scope">
		         <el-button
		           size="mini"
		           @click="handleEdit(scope.$index, scope.row)">编辑</el-button>
		         <el-button
		           size="mini"
		           type="danger"
		           @click="handleDelete(scope.$index, scope.row)">删除</el-button>
		       </template>
		     </el-table-column>
		   </el-table>
		   <el-pagination
		     background
		     layout="prev, pager, next"
		     :total="total"
			 :page-sizes="pages"
			 :current-page="currentPage"
			 :page-size="pageSize"
			 @current-change="currentChange">
		   </el-pagination>
		   <el-dialog :title="title" :visible.sync="dialogVisible" width="30%" :before-close="handleClose">
		         <el-form ref="form" :model="form" label-width="80px">
		           <el-form-item label="商品id">
		             <el-input v-model="form.id"></el-input>
		           </el-form-item>
		           <el-form-item label="商品名称">
		             <el-input v-model="form.sname"></el-input>
		           </el-form-item>
				   <el-form-item label="商品价格">
				     <el-input v-model="form.sprice"></el-input>
				   </el-form-item>
				   <el-form-item label="商品数量">
				     <el-input v-model="form.snum"></el-input>
				   </el-form-item>
				   <el-form-item label="商品备注">
				     <el-input v-model="form.desc"></el-input>
				   </el-form-item>
		         </el-form>
		         <span slot="footer" class="dialog-footer">
		           <el-button @click="dialogVisible = false">取 消</el-button>
		           <el-button type="primary" @click="save">确 定</el-button>
		         </span>
		       </el-dialog>
		   
	</div>
</template>

<style>
  .el-table .warning-row {
    background: oldlace;
  }

  .el-table .success-row {
    background: #f0f9eb;
  }
</style>


<script>
  export default {
    data() {
      return {
		currentPage:1,
		pageSize:5,
		total:10,
		dialogVisible: false,
		form: { id: "", sname: "", sprice: "", snum: "", img: "", desc:""},
        tableData: [{
          id: '1',
          sname: '薯片',
          sprice: '10元',
		  snum: '10'
        }, {
          id: '2',
          sname: '可乐',
          sprice: '10元',
          snum: '10'
        }, {
          id: '3',
          sname: '雪碧',
          sprice: '10元',
          snum: '10'
        }, {
          id: '4',
          sname: '饼干',
          sprice: '10元',
          snum: '10'
        }],
        search: ''
      }
    },
    methods: {
      handleEdit(index, row) {
        console.log(index, row);
      },
      handleDelete(index, row) {
        console.log(index, row);
      },
	  tableRowClassName({row, rowIndex}) {
	          if (rowIndex%2 == 0) {
	            return 'warning-row';
	          } else {
	            return '';
	          }
	    },
		currentChange(val){
			console.log(val)
			this.$data.currentPage = val;
		},
		// 编辑
		handleEdit(index, rows) {
		      this.title = "编辑商品";
		      this.dialogVisible = true;
		      this.form.id = rows.id;
		      this.form.sname = rows.sname;
		      this.form.sprice = rows.sprice;
		      this.form.snum = rows.snum;
			  this.form.desc = rows.desc;
		      console.log(index + "->" + rows.sname);
		},
		// 删除
		handleDelete(index, rows) {
			this.tableData.splice(index,1);
		      // this.userData.splice(index, 1);
		},
    },
	
  }
</script>