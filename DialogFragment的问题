java.lang.IllegalStateException: Can not perform this action after onSaveInstanceState
    at androidx.fragment.app.b.y(FragmentManagerImpl.java:1536)
    at androidx.fragment.app.b.a(FragmentManagerImpl.java:1558)
    at androidx.fragment.app.a.a(BackStackRecord.java:317)
    at androidx.fragment.app.a.commit(BackStackRecord.java:282)
    at androidx.fragment.app.DialogFragment.show(DialogFragment.java:155)
    at com.yiimuu.wool.ui.task.app.b.a(TaskAppsFragment.kt:162)
    at com.yiimuu.wool.ui.task.app.b$b$a.run(TaskAppsFragment.kt:61)
    at android.os.Handler.handleCallback(Handler.java:733)
    at android.os.Handler.dispatchMessage(Handler.java:95)
    at android.os.Looper.loop(Looper.java:136)
    at android.app.ActivityThread.main(ActivityThread.java:5314)
    at java.lang.reflect.Method.invokeNative(Native Method)
    at java.lang.reflect.Method.invoke(Method.java:515)
    at com.android.internal.os.ZygoteInit$MethodAndArgsCaller.run(ZygoteInit.java:864)
    at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:680)
    at dalvik.system.NativeStart.main(Native Method)


报错的原因：dialog.show()方法的内部使用了commit()方法提交事务，某些时候因为状态异常而报错。
解决方法就是使用commitAllowingStateLoss()方法，具体如下所示：

解决方法：不调用dialog.show()方法，而是调用getSupportFragmentManager().beginTransaction().add(dialog, "tag").commitAllowingStateLoss();

可以通过isStateSaved()判断是否已经执行过onSaveInstanceState().