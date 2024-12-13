<template>
  <WjFlexGrid :items-source="jsonData">
    <WjFlexGridColumn header="worksheetId" binding="worksheetId" :visible="false" />
    <WjFlexGridColumn header="裁床號" binding="bedNum" isReadOnly="true" :width="80" />
    <WjFlexGridColumn
        header=" 開裁日期"
        binding="cutDate"
        :isRequired="false"
        :editor="editors.inputDate"
        :width="120"
        format="yyyy-MM-dd"
    />git
  </WjFlexGrid>
</template>
<script setup lang="ts">
import { WjFlexGridColumn,  WjFlexGrid } from '@mescius/wijmo.vue2.grid';
import {ref} from "vue";
import '@mescius/wijmo.styles/wijmo.css';
import  {CollectionView} from "@mescius/wijmo";
import {InputDate} from "@mescius/wijmo.input";
//下拉框
const editors = {
  inputDate: new InputDate(document.createElement('div')),
};
const WorksheetCutItemListCollectionView = ref<CollectionView | null>(null);
// 示例 JSON 数据
const jsonData = [
  {
    flag: null,
    worksheetCutItemId: 39,
    worksheetCutId: 30,
    bedNum: 1,
    cutDate: '2024-09-02 00:00:00',
    fabricType: '顶级丝绸',
    colorTypeSvId: 57182,
    statusSvId: 35,
    createBy: 1,
    createDate: '2024-09-19 15:34:36',
    updateBy: 1,
    updateDate: '2024-12-05 14:39:58',
    selectedSizeName: 'XL, L, M',
    barcodeQty: 6739,
    minBarcodeNum: 1,
  },
];

// // 将 JSON 数据包装到 CollectionView 中
// WorksheetCutItemListCollectionView.value = new CollectionView(jsonData);
// // 打印结果以验证
// console.log('xxxxx', WorksheetCutItemListCollectionView.value);
</script>

<style scoped>

</style>
