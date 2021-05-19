# bm-tender-step

用于本末项目内投标业务类的步骤条

# 安装

```shell
npm install bm-tender-step -s
```

```javascript
import Vue from 'vue'
import bmTenderStep from 'bm-tender-step'
import 'bm-tender-step/bmTenderStep.less'
Vue.use(bmTenderStep)
```

```html
<template>
    <div>
        <step :stepList="progress"></step>            
    </div>
</template>

<script>
export default {
    data () {
        return {
            progress: [
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
    }
}
</script>
```

## 参数注解

progress: 步骤条数组

组件自动根据数组长度计算单个步骤宽度, 无需设置样式



