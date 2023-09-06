
# https://developers.google.com/maps/documentation/android-sdk/map-with-marker?hl=zh-tw
# https://developers.google.com/maps/documentation/android-sdk/map?hl=zh-tw

Note: for kotlin
in MainActivity.kt
1. Alt + Enter to make reference pass
2. package com.example.{your project}
3. import com.example.ubikemap.R.layout.activity_main
4. "setContentView(activity_main)" not "setContentView(R.layout.activity_maps)"
5. val mapFragment: SupportMapFragment? = supportFragmentManager
   .findFragmentById(R.id.map) as SupportMapFragment?
   mapFragment!!.getMapAsync(this)

    ==> mapFragment!!
    not 

   val mapFragment = supportFragmentManager.findFragmentById(R.id.map) as? SupportMapFragment
   mapFragment?.getMapAsync(this)

in activity_main.xml
1. Add <fragment ... 
         android:id="@+id/map" ... />
   inside <androidx.constraintlayout.widget.ConstraintLayout >
           ... </androidx.constraintlayout.widget.ConstraintLayout>

in AndroidManifest.xml
1. add <meta-data
   android:name="com.google.android.geo.API_KEY"
   android:value="${MAPS_API_KEY}" />
    inside <application> ... </application>

