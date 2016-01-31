ViewServer is a simple class you can use in your Android application
to use the HierarchyViewer inspection tool.

ViewServer requires the Android SDK r12 or higher.
http://developer.android.com/sdk/index.html

Quick Start
-----
 * Verify that you need this library([newer versions of Android don't][setup])
 
If you do need this library then follow these directions:
 * Include the ViewServer library(easy directions found [here][jitpack])
 * Your application __must__ require the INTERNET permission
 * The recommended way to use this API is to register activities when they are created, and to unregister them when they get destroyed:

```java
public class MyActivity extends Activity {
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        // Set content view, etc.
        ViewServer.get(this).addWindow(this);
    }

    public void onDestroy() {
        super.onDestroy();
        ViewServer.get(this).removeWindow(this);
    }

    public void onResume() {
        super.onResume();
        ViewServer.get(this).setFocusedWindow(this);
    }
}
 ```
 [setup]:http://developer.android.com/intl/es/tools/performance/hierarchy-viewer/setup.html
 [jitpack]: https://jitpack.io/#romainguy/ViewServer


Please refer to the documentation in ViewServer.java for more info.
