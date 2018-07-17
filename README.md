# dialoger
jsWeb弹出框(无依赖)，包括Alert、Confirm、Toast、Loading、Notify、Modal


## Loading
```javascript
//打开loading
dialoger.$loading.open({mes: '请稍后'});
//关闭loading
dialoger.$loading.close();
```

## Alert
```javascript
//打开Alert框
dialoger.$alert({mes: '这是提示的信息'});
//打开Alert框，带标题，点击确定按钮执行回调
dialoger.$alert({mes: '这是提示的信息', title: '标题', callback: function(){
  console.log("你点击了确定");
}});
```

## Confirm
```javascript
//普通的确认框
dialoger.$confirm({
    mes: '点击确定按钮试下?', 
    callback: function() {
      dialoger.$toast({mes: '你点击了OK'})
    }
  });
//自定义按钮的，带标题的
dialoger.$confirm({
    title: '确认提示',
    mes: '确定要删除吗?', 
    btns: [
      {txt: '不删除', stylename: 'default-btn', callback: function(){
        dialoger.$toast({mes: '不删除'})
      }},
      {txt: '考虑一下', callback: function(){
        dialoger.$toast({mes: '很谨慎'})
      }},
      {txt: '删除吧', callback: function() {
        dialoger.$toast({mes: '已经删除'})
      }}
    ]
  });
```

## Toast
```javascript
//正确的提示
dialoger.$toast({mes: '成功', type: 'success'});
//错误的提示
dialoger.$toast({mes: '错误', type: 'error'});
//不带图标的提示,timeout默认2000
dialoger.$toast({mes: 'This is toast', timeout: 3000});
```


## Notify
```javascript
//顶部提示,timeout 默认3000
dialoger.$notify({mes: '这是提示的信息', timeout: 5000});
```


## Modal
```javasctipt
//简单的弹出层
dialoger.$modal.open({
    id: 'modalid',
    body: '<p>This is modal!</p>'
  });
dialoger.$modal.open({
    id: 'modalid',
    title: '来自于ModalBody里的内容',
    body: document.querySelector('#modalBody')
  });
```




