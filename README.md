<h1>NMEX Android ads fix</h1>

<p>Use <a href="http://code.google.com/p/nmex/">NMEX</a> to incorporate ads into your NME applications.</p>

<ol>
<li><p>Copy the nmex folder and the java folder to your src folder.</p></li>
<li><p>Copy the <code>AndroidManifest.xml</code>, <code>MainActivity.java</code>, <code>Android</code> folder and <code>application.nmml</code> to your root project directory</p></li>
<li><p>Go to your <code>Motion-Twin\haxe\lib\ nme\3,4,4\ templates\default\ android\ template\src\org\haxe\ nme</code> folder and open the <code>MainView.java</code>. Change the class to public. Then, open the <code>GameActivity.java</code> and change the member variable <code>mView</code> to public and <code>static GameActivity activity </code> to <code> public static GameActivity activity</code>.</p></li>
<li><p>Go to your <code>C:\Motion-Twin\haxe\lib\ nme\3,4,4\ templates\default\ android\ template</code> folder and open the <code>build.xml</code> file. Change the target
value to <code>android-13</code>. You will need to ensure you have downloaded the Android 3.3 (android 13) SDK with the SDK manager.</p></li>
<li><p>Create an Admob account. Click add new app/site and enter the details requested. Afterwards, click on manage and then you will see your publisherID.</p></li>
<li><p>Call <code>AD.showAd()</code> and pass in your publisherID </p></li>
<li><p>Find your device ID by running logcat and examinine the output. This can be done by opening a command prompt, changing directory to your AndroidSDK platform tools and running <code>adb logcat &gt; logcat.txt</code>. Then run your app. After it has finished starting, close the command prompt and open the generated logcat.txt file. Search it for your device ID. Then, open the <code>AdActivity.java</code> file in the com\pixelpounce\ads folder. Replace the <code>AdRequest.TEST_EMULATOR</code> with your device id. Finally uncomment the <code>adView.loadAd(request)</code></p></li>
</ol>