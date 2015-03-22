> **调用JSONArray.remove ()报错**

JSONArray的remove方法是在API level 19时加入的，在低版本调用时会出现错误。

**代码位置：** 

``` java
VFY:
 unable to resolve virtual method 9294: Lorg/json/JSONArray;.remove (I)Ljava/lang/Object;
``` 

**解决方法：** 

``` java
public JSONArray remove(JSONArray jsonArray,int index){ 
             JSONArray mJsonArray  = new JSONArray();

             if(index<0)    return mJsonArray;
             if(index>jsonArray.length())   return mJsonArray;

             for( int i=0;i<index;i++){
                try {
                    mJsonArray.put(jsonArray.getJSONObject(i));
                    } catch (JSONException e) {
                            e.printStackTrace();
                    }
                }   

             for( int i=index+1;i< jsonArray.length();i++){
                try {
                    mJsonArray.put(jsonArray.getJSONObject(i));
                    } catch (JSONException e) {
                            e.printStackTrace();
                    }
                 }
             return mJsonArray;
}
``` 