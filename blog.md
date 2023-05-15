## 封装函数 f，使 f 的 this 指向指定的对象

```
function bindThis(f, oTarget) {
    /**
    return function(){
       return f.apply(oTarget,arguments)
    }
    */
    return function(){
        return f.call(oTarget,...arguments)
    }
    /**
    return f.bind(oTarget)
    */
}
```

## 查找两个节点的最近的一个共同父节点，可以包括节点自身

```
function commonParentNode(oNode1, oNode2) {
    while (oNode1) {
        oNode1 = oNode1.parentNode;
        if(oNode1.contains(oNode2)) {
            return oNode1
        }
    }
}
```

## 根据包名，在指定空间中创建对象

```
function namespace(oNamespace, sPackage) {
    sPackage.split('.').reduce((prev,curr)=>{
        prev[curr] = Object.assign({},prev[curr])
        return prev[curr]
    },oNamespace)
    return oNamespace
}
```

## 为 Array 对象添加一个去除重复项的方法

```
Array.prototype.uniq = function () {
    return Array.from(new Set(this))
}

```


