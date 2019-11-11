<template>
	<view>
		<view class="syBox">
		<!--第一层-->
		<view class="ycBox">
			<view class="ycyBox">
				我的任务栏 
			</view>
		</view>
		<!--第二层  -->
		<view class = "navBox">
			
			<view class = "navS">
				<view class = "ercBox">我的任务</view>
				<image class = "ercyBox" src = "../../static/img/xbj/sd_06.gif" mode = "aspectFill"></image> <!-- 添加图片   mode = "aspectFill" ：切割图片  -->
			</view>

			<view class="navj">
				<view>发布任务</view>
				<image class = "ercsBox" src = "../../static/img/xbj/555_06.gif" mode = "aspectFill"></image>
			</view>
		</view>
		
		
		<!-- 第三层 -->
		<view class = "appBox" v-for = "(item,index) in list" :key = "index" >  <!--利用循环的方法把重复的东西打印出来v-for = "(item,index) in list" :key = "index" 键值key一定要添加-->
			<view class = "fdBox">
				<view class="jiBox">
					<view class="snav">
						{{item.title}} 
					</view>
				</view> 
				<view class="scBox">
					{{item.money}}
				</view> 
			</view>
			
			<view class="scerBox">
					<image class="scs" src = "../../static/img/xbj/1_01_14.gif" >
					</image>
					<text class="scsqBox">
						{{item.text}}
					</text>		
			</view>
			
			<view class="scsss">
				<view>
					<image class="scwBox" src = "../../static/img/xbj/1_01_20.gif" >
					</image>
						<text class="sclBox">
							{{item.time}}
						</text> 
				</view>
				
				<!-- 利用循环语句输出打印-->
				<view v-if="item.status == 0" class="scqBox">
					<view>
						<image class="scbBox" src = "../../static/img/xbj/3_21.gif" >
						</image>
							进行中
						</view>
				</view>
				
				<view v-else-if = "item.status == 1" class="scjBox">
					<view>
						<image class="scshiBox" src = "../../static/img/xbj/1_07.gif">
						</image>
							已收款
					</view>
				</view>
				
				<view v-else-if = "item.status == 2" class="scsyBox">
					<view>
						<image class="scshier" src = "../../static/img/xbj/8_07.gif">
						</image>
							未付款
					</view>
					
				</view>
				<view v-else-if = "item.status == 3" class="scshisBox">
					<view>
						<image class="scshissBox" src = "../../static/img/xbj/3_21.gif">
						</image>
							已接受
					</view>
					
				</view>
				<view v-else-if = "item.status == 4" class="scswBox">
					<view>
						<image class="scslBox" src = "../../static/img/xbj/3_21.gif">
						</image>
							待接收
					</view>
					
				</view>
			</view>
			</view>
		</view>
		</view>
<!--  -->
	</view>
</template>

<script>
	
export default {
	data() {
		return {
			title: '',
		
			list:[  //利用list调用所有
				{  //第一个文本
					title:'全案处理',
					money:"AUD 300",
					text:"500签证全安处理",
					time:'2019-05-01',
					status:0
				},
				{ //第二个文本
					title:'翻译',
					money:"AUD 300",
					text:"学生成绩单翻译",
						time:'2019-05-01',
					status:1
				},
				{ //第三个文本
					title:'其他',
					money:"AUD 300",
					text:"学生个人陈述验证",
						time:'2019-05-01',
					status:2
				},
				{ //第四个文本
					title:'其他',
					money:"AUD 300",
					text:"学生个人陈述验证",
						time:'2019-05-01',
					status:3
				},
				{ //第五个文本
					title:'其他',
					money:"AUD 300",
					text:"学生个人陈述验证",
						time:'2019-05-01',
					status:4
				}
				
			]
		};
	},
	
	//页面加载自动调用的方法   可以加载数据
	onLoad() {
		
	},
	
	//方法写的地方
	methods: {
		
		newTime(){
			return new Date();  //获取当前时间
		},
	}
};
</script>

<style lang="scss" scoped>  //链接  []pages.json
//范围scoped
.ycBox{
	background:white;  	//背景颜色
	width: 100%;  		 //背景宽度取100%
	height: 100% 		//背景高度取100%
}

.syBox{
	background: #F1F1F1;  
}

.ycyBox{
	font-size: 45rpx;  //文字大小
	margin: 45rpx; //下方间隔
	font-weight: bold; //文字加粗
}

.ercBox{
	font-size: 31rpx;//字体大小
}

.ercyBox{
	width: 59rpx;
	height: 61rpx;
	text-align: left;  //文字左靠
}

.ercsBox{
	width: 59rpx;
	height:61rpx;
	margin-left: 16.5rpx; //
	text-alige:right;//文本向右
}

.jiBox{
	border-left:9rpx #007AFF solid; //边框左上角挂件
}

.navBox {
	border-bottom-right-radius:60rpx; //边框右下角呈圆角
	border-bottom-left-radius:60rpx;//边框左下角呈圆角
	background: white;//背景色为白色
	width:100%;//整个屏幕得宽度
	height: 100%;//整个屏幕的高度
	display: flex;  //弹性盒模型
	justify-content: center;//居中
	align-items: center;  //文本与文字居中对齐
	//text-align: center;
}

.appBox {
	background: white;
	margin-left:29rpx;
	margin-right: 29rpx;
	margin-bottom: 29rpx;
	margin-top: 29rpx;
	height: 260rpx;
	width: 685rpx;
	border-top-left-radius: 20rpx;//左上角呈圆角
	border-top-right-radius: 20rpx;//右上角呈圆角
	border-bottom-right-radius:20rpx;
	border-bottom-left-radius:20rpx;
	border: 2rpx solid white;//边框大小为2rpx 颜色为白色
}

.navS {
	background: #3f536e;
	width: 320rpx;
	height: 125rpx;
	border: 2rpx solid #999999;
	margin: 30rpx 25rpx;
	border-top-left-radius: 20rpx;
	border-top-right-radius: 20rpx;
	border-bottom-right-radius:20rpx;
	border-bottom-left-radius:20rpx;
	display: flex;
	justify-content: space-around;//对齐边框的两端
	align-items: center;//图片与文本对齐
}

.snav{
	margin-left: 28rpx;//文本向右移动28个rpx
	font-size: 28rpx;
}

.scBox{
	background: #007AFF;
	width:134;
	height: 50;
	font-size: 21rpx;
	color: white;
	margin-right: 40rpx;
}

.scerBox{
	display: flex;
	align-items: center;
	margin-top: 28rpx;
}

.scs{
	width: 45rpx; 
	height:20rpx;
	margin-left: 28rpx;
}

.scsss{
	display: flex;
	align-items: center;
	margin-top:25rpx;
	display: flex;
	justify-content:space-between;
}

.scwBox{
	width: 20rpx; 
	height: 20rpx;
	margin-left: 28rpx;
}

.sclBox{
	font-size: 21rpx;
	margin-right: 40rpx;
} 

.scqBox{
	font-size:21rpx;
	color: yellow;
	margin-right: 40rpx;
}

.scbBox{
	width:20rpx;
	height: 20rpx;
}

.scjBox{
	font-size: 21rpx;
	color: black;
	margin-right: 40rpx;
}

.scshiBox{
	width:20rpx;
	height: 20rpx;
	align-items: center;
}

.scsyBox{
	font-size: 21rpx;
	color: red;
	margin-right: 40rpx;
}

.scshier{
	width:20rpx;
	height: 20rpx;
	align-items: center;
	color: red;
}
 
.scshisBox{
	font-size: 21rpx;
	color: yellow;
	margin-right: 40rpx;
}

.scshissBox{
	width:20rpx;
	height: 20rpx;
	align-items: center;
}

.scswBox{
	font-size: 21rpx;
	color: yellow;
	margin-right: 40rpx;
}

.scslBox{
	width:20rpx;height:20rpx;
	align-items: center;
}

.scsqBox{
	font-size: 21rpx;
	}
.navj {
	border-top-left-radius: 20rpx;
	border-top-right-radius: 20rpx;
	border-bottom-right-radius:20rpx;
	border-bottom-left-radius:20rpx;
	font-size: 30rpx;
	justify-content: space-around;
	display: flex;
	align-items: center;
	width: 320rpx;
	margin-left: 16.6rpx;
	height: 125rpx;
	border: 2rpx solid #999999;
	margin: 30rpx 25rpx;
}

.fdBox{
	margin-bottom: 40rpx;
	margin-top: 40rpx;
	width: 700rpx;
	justify-content: space-between;
	display: flex;
	align-items:  flex-start;
	align-content:space-between;
	margin-top: 28rpx;
}

</style>
