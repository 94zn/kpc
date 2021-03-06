---
title: 基本用法
order: 0
---

`Tabs`的基本用法。需要使用`v-model`来指定选中标签。


```vdt
import {Tabs, Tab} from 'components/tabs';

<div>
    <Tabs data={{ [
        {
            text: '入站规则',
            value: 'rulein',
        },
        {
            text: '出站规则',
            value: 'ruleout',
        },
        {
            text: '关联云主机',
            value: 'relatedVM',
        }
    ] }} value="relatedVM"  style="margin: 20px;"/>

    <Tabs v-model="tab2" style="margin: 20px;">
        <Tab value="rulein">入站规则</Tab>
        <Tab value="ruleout">出站规则</Tab>
        <Tab value="relatedVM">关联云主机</Tab>
    </Tabs>
    <div style="margin: 20px;" v-if={{ self.get('tab2') == 'rulein' }}>入站规则</div>
    <div style="margin: 20px;" v-else-if={{ self.get('tab2') == 'ruleout' }}>出站规则</div>
    <div style="margin: 20px;" v-else>关联云主机</div> 
    
</div>

```
```js

export default class extends Intact {
    @Intact.template()
    static template = template;
    defaults(){
        return {
            tab1:'',
            tab2:'ruleout'
        }
    }
}
```
```styl
.k-checkbox
    margin-right 20px
```
