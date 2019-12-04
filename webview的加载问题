##WebChromeClient的getDefaultVideoPoster
使用webview的视频全屏播放功能，WebChromeClient的回调方法之一getDefaultVideoPoster需要Override一下，

```
java.lang.NullPointerException: Attempt to invoke virtual method &#39;int android.graphics.Bitmap.getWidth()&#39; on a null object reference
	at com.android.webview.chromium.WebViewContentsClientAdapter.getDefaultVideoPoster(WebViewContentsClientAdapter.java:1142)
	at org.chromium.android_webview.DefaultVideoPosterRequestHandler$1.run(DefaultVideoPosterRequestHandler.java:39)
	at android.os.Handler.handleCallback(Handler.java:815)
	at android.os.Handler.dispatchMessage(Handler.java:104)
	at android.os.Looper.loop(Looper.java:224)
	at android.app.ActivityThread.main(ActivityThread.java:5958)
	at java.lang.reflect.Method.invoke(Native Method)
	at java.lang.reflect.Method.invoke(Method.java:372)
	at com.android.internal.os.ZygoteInit$MethodAndArgsCaller.run(ZygoteInit.java:1113)
	at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:879)
```

####解决方案

```
WebView内部报空指针：解决方法是重写
//java版本
class MyWebChromClient extends WebChromeClient{
@Override
public Bitmap getDefaultVideoPoster() {
    try{
        //这个地方是加载h5的视频列表 默认图   点击前的视频图
        LogUtil.w("全网搜索","   加载视频默认图片");
        return BitmapFactory.decodeResource(getApplicationContext().getResources(),
                R.drawable.icon_default);

    }catch(Exception e){
        LogUtil.w("全网搜索","   加载视频默认图片失败,,,,,,,,,,,,,");
        return super.getDefaultVideoPoster();
    }

}
}

//kotlin版本
override fun getDefaultVideoPoster(): Bitmap? {
                return try {
                    BitmapFactory.decodeResource(
                        WoolApp.instance.resources,
                        R.drawable.animated_rotate
                    )
                } catch (e: Exception) {
                    super.getDefaultVideoPoster()
                }
            }
```