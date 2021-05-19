<template>
	<div class="step-main">
		<div class="step_item"
             v-for="(i, index) in stepList"
             :key="'stepList' + index"
             :class="{active: i.state}">
			<div class="icon">
				<i class="iconfont iconbangzhu"></i>
			</div>

			<div class="index_box">
				<div class="index">{{'0' + (index + 1)}}</div>
				<div class="vertical_bar"></div>
                <div class="line"></div>
			</div>

			<div class="info_box">
				{{i.sname}}
			</div>

			<div class="circle" v-show="index < (stepList.length - 1)"></div>
		</div>

        <div class="mline"></div>
	</div>
</template>

<script>
export default {
    name: 'BmTenderStep', // 步骤条
    data() {
        return {
            stepList: [
                {
                    sname: '确认参与',
                    stateYes: '已确认',
                    stateNo: '待确认',
                    state: true,
                    keyName: 'confirmParticipation'
                },
                {
                    sname: '招标文件下载',
                    stateYes: '已下载',
                    stateNo: '待下载',
                    state: true,
                    keyName: 'downloadBiddingDocuments'
                },
                {
                    sname: '保证金支付',
                    stateYes: '已支付',
                    stateNo: '待支付',
                    state: true,
                    keyName: 'marginPayment'
                },
                {
                    sname: '投标文件递交',
                    stateYes: '已递交',
                    stateNo: '待递交',
                    state: true,
                    keyName: 'submissionTenderDocuments'
                },
                {
                    sname: '开标',
                    stateYes: '已开标',
                    stateNo: '待开标',
                    state: true,
                    keyName: 'bidOpening'
                },
                {
                    sname: '标书解密',
                    stateYes: '已解密',
                    stateNo: '待解密',
                    state: true,
                    keyName: 'declassificationTender'
                },
                {
                    sname: '标书费发票',
                    stateYes: '已开票',
                    stateNo: '待开票',
                    state: true,
                    keyName: 'invoiceTenderFee'
                },
                {
                    sname: '保证金退回',
                    stateYes: '已退回',
                    stateNo: '待退回',
                    state: true,
                    keyName: 'RefundDeposit'
                }
            ]
        }
    },
    mounted() {
        var step_item_list = document.getElementsByClassName('step_item')
        // console.log(step_item_list)
        for(var i = 0; i < step_item_list.length; i++) {
            step_item_list[i].style.width = (100 / step_item_list.length).toFixed(2) + '%'
        }
    }
}
</script>

<style lang="less">
.step-main {
    display: flex;
	.step_item {
        color: #777;
        position: relative;
		.icon {
			width: 68px;
			height: 68px;
			background: #ededed;
			text-align: center;
			line-height: 68px;
			border-radius: 50%;
			margin: 0 auto;
            font-size: 50px;
            position: relative;
            top: 10px;
            font-size: 50px;
            color: white;
		}

		.index_box {
            height: 90px;
            position: relative;
			.index {
                position: absolute;
                top: 50%;
                left: 50%;
                -webkit-transform: translateY(-50%) translateX(-50%);
                transform: translateY(-50%) translateX(-50%);
				border-radius: 50%;
				width: 30px;
				height: 30px;
				margin: 0 auto;
				background: #ededed;
				text-align: center;
                line-height: 30px;
                z-index: 1000;
                font-size: 12px;
                font-family: DIN;
                font-weight: 500;
                color: #666666;
			}
			.vertical_bar {
                position: absolute;
                top: 60px;
				width: 50%;
				box-sizing: border-box;
				border-right: 2px solid #ededed;
				height: 30px;
				margin-left: 1px;
            }
            .line {
                width: 100%;
                height: 2px;
                background: #ededed;
                position: absolute;
                top: 50%;
                -webkit-transform: translateY(-50%);
                transform: translateY(-50%);
                z-index: 999;
            }
		}

		.info_box {
			text-align: center;
			line-height: 40px;
            color: #333333;
            height: 68px;
            font-family: PingFang SC;
		}

		.circle {
			width: 8px;
            height: 8px;
            border-radius: 50%;
            background: #ededed;
            position: absolute;
            top: 50%;
            right: -4px;
            -webkit-transform: translateY(-50%);
            transform: translateY(-50%);
            z-index: 99999;
        }
	}

	.active {
		color: white;
		.icon {
            background: #519efa;
		}

		.index_box {
			.index {
                background: #519efa;
                color: white;
			}
			.vertical_bar {
				border-right: 2px solid #519efa;
            }
            .line {
                background: #519efa;
            }
        }
        
        .circle {
            background: #519efa;
        }

		.info_box {
			color: #519efa;
		}
    }
}
</style>