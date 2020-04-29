//字符串转化为数字
思路:在此并没有使用原生方法parseInt()、Number()将字符串转化为数字,而是通过ASCII码进行判断
其中常见字符对应的ASCII为
a-z 97-122
A-Z 65-90
0-9 45-57
function convertStringToNumber(s){
    var numArr = [];//用来存放数组字符串
    for(let i = 0;i<s.length;i++){
        //0-9对应的ascii为45-57,遇到第一个不是数字的字符时，跳出循环
        if(s.charCodeAt(i)>57){
            return Number(numArr.join(''))
        //不是从0开始，判断到第一个非数字字符时结束
        }else{
            numArr.push(s[i])
        }
    }
    return Number(numArr.join(''))
}
//数字转化为字符串
function convertNumberToString (num){
    return num+''
    //return num.toString()
    //return String(num)
}



javaScript分为宿组对象、内置对象（固有对象、原生对象、普通对象）
宿主对象主要是浏览器对象-window对象
内置对象：
a.固有对象：（来自重学前端中winter老师）
  var set = new Set();
  var objects = [
      eval,
      isFinite,
      isNaN,
      parseFloat,
      parseInt,
      decodeURI,
      decodeURIComponent,
      encodeURI,
      encodeURIComponent,
      Array,
      Date,
      RegExp,
      Promise,
      Proxy,
      Map,
      WeakMap,
      Set,
      WeakSet,
      Function,
      Boolean,
      String,
      Number,
      Symbol,
      Object,
      Error,
      EvalError,
      RangeError,
      ReferenceError,
      SyntaxError,
      TypeError,
      URIError,
      ArrayBuffer,
      SharedArrayBuffer,
      DataView,
      Float32Array,
      Float64Array,
      Int8Array,
      Int16Array,
      Int32Array,
      Uint8Array,
      Uint16Array,
      Uint32Array,
      Uint8ClampedArray,
      Atomics,
      JSON,
      Math,
      Reflect];
  objects.forEach(o => set.add(o));

  for(var i = 0; i < objects.length; i++) {
      var o = objects[i]
      for(var p of Object.getOwnPropertyNames(o)) {
          var d = Object.getOwnPropertyDescriptor(o, p)
          if( (d.value !== null && typeof d.value === "object") || (typeof d.value === "function"))
              if(!set.has(d.value))
                  set.add(d.value), objects.push(d.value);
          if( d.get )
              if(!set.has(d.get))
                  set.add(d.get), objects.push(d.get);
          if( d.set )
              if(!set.has(d.set))
                  set.add(d.set), objects.push(d.set);
      }
  }
  //set共989个
b.原生对象：
 b1:基本类型：Boolean,String,Number,Symbol,Object
 b2:基本功能和数据结构：Array,Date,RegExp,Promise,Proxy,Map,WeakMap,Set,WeakSet,Function
 b3:错误类型：Error,EvalError,RangeError,ReferenceError,SyntaxError,TypeError,URIError
 b4:二进制操作：ArrayBuffer,SharedArrayBuffer,DateView
 b5:带类型的数组：Float32Array,Float64Array,Int8Array,Int16Array,Int32Array,Uint8Array,Uint16Array,Uint32Array,Uint8ClampedArray
原生对象需要使用new运算进行创建新的对象

