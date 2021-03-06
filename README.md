# CollapsingToolbarLayout-Example
A very SIMPLE example shows how collapsing tool bar layout works.   
![alt tag](https://github.com/JianhuiZhu/CollapsingToolbarLayout-Example/blob/master/1185.gif)      

##Library:    
      # material librarys
      compile 'com.android.support:appcompat-v7:22.2.0'
      compile 'com.android.support:design:22.2.0'   
      # view binder   
      compile 'com.jakewharton:butterknife:7.0.1'   
  
# Layout File   
      <?xml version="1.0" encoding="utf-8"?>
      <android.support.design.widget.CoordinatorLayout
          xmlns:android="http://schemas.android.com/apk/res/android"
          xmlns:app="http://schemas.android.com/apk/res-auto"
          android:layout_width="match_parent"
          android:layout_height="match_parent"
          android:fitsSystemWindows="true"
    style="@style/Theme.AppCompat.Light.NoActionBar">
      <android.support.design.widget.AppBarLayout
            android:layout_height="192dp"
            android:layout_width="match_parent"
           xmlns:android="http://schemas.android.com/apk/res/android"
           xmlns:app="http://schemas.android.com/apk/res-auto"
           android:theme="@style/ThemeOverlay.AppCompat.Dark.ActionBar">
    <!-- contentScrim is used for -->
        <android.support.design.widget.CollapsingToolbarLayout
            android:id="@+id/collapsingToolbar"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
           app:contentScrim="?attr/colorPrimary"
           app:layout_scrollFlags="scroll|exitUntilCollapsed">

        <ImageView
            android:id="@+id/toolbar_background"
            android:layout_height="wrap_content"
            android:layout_width="match_parent"
            android:src="@drawable/squirrel"
            android:scaleType="centerCrop"
            android:fitsSystemWindows="true"
            app:layout_collapseMode="parallax" />

           <android.support.v7.widget.Toolbar
              android:id="@+id/toolbar"
              android:layout_width="match_parent"
              android:layout_height="?attr/actionBarSize"
              app:layout_collapseMode="pin"
             android:layout_gravity="right|bottom"
             app:popupTheme="@style/ThemeOverlay.AppCompat.Light"/>

        </android.support.design.widget.CollapsingToolbarLayout>

      </android.support.design.widget.AppBarLayout>
          <android.support.v4.widget.NestedScrollView
             android:layout_width="match_parent"
              android:layout_height="match_parent"
              android:fitsSystemWindows="true"
             app:layout_behavior="@string/appbar_scrolling_view_behavior">
          <LinearLayout
              android:layout_width="match_parent"
              android:layout_height="wrap_content"
              android:orientation="vertical">
              <TextView
                 android:layout_width="match_parent"
                  android:layout_height="wrap_content"
                  android:text="@string/description"
                  android:layout_gravity="fill_vertical"
                  android:maxEms="8"
                  android:textStyle="bold"
                  android:textSize="18dp"/>
            </LinearLayout>
       </android.support.v4.widget.NestedScrollView>
      </android.support.design.widget.CoordinatorLayout>
