> **No package identifier when getting value for resource number 0x00000003**

**错误提示信息:**
``` java
W/ResourceType(6991): 
No package identifier when getting value for resource number 0x00000003
W/dalvikvm(8564): threadid=1: thread exiting with uncaught exception (group=0x415f7498)
```

**代码位置：** 
``` java
private int orderAmount;  
textView.setText(order.orderAmount);  
``` 

**错误原因：** 
主要是因为TextView的setText方法会把传入的int类型的变量当做资源Id到项目中查询资源，而资源中却找不到相应的数值，就会报NotFoundException的错误。

在Android中利用id来索引资源的地方很多（如:Toast.makeText()等），所以如果不小心往方法中传入int类型的参数，虽然编译时IDE不会报错，但是运行时，很容易因找不到对应的资源而报错。
解决方法：转换为字符串类型
``` java
textView.setText(String.valueOf(order.orderAmount));  
``` 