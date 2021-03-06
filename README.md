EasyTabs
===================


EasyTabs is a library that creates Material Design tabs in less the 5 minuts with super easy interface and tons of styling options.

----------
![gif](https://raw.githubusercontent.com/gilgoldzweig/EasyTabs/master/Mediafiles/slidingtablayout.gif)   <img style="user-select: none; cursor: zoom-in;"
src="https://raw.githubusercontent.com/gilgoldzweig/EasyTabs/master/Mediafiles/animation.gif" width="240" height="427">   <img style="user-select: none; cursor: zoom-in;"
src="https://raw.githubusercontent.com/gilgoldzweig/EasyTabs/master/Mediafiles/image1.png" width="240" height="427">

<img style="user-select: none; cursor: zoom-in;" src="https://raw.githubusercontent.com/gilgoldzweig/EasyTabs/master/Mediafiles/image2.png" width="240" height="427">   <img style="user-select: none; cursor: zoom-in;" src="https://raw.githubusercontent.com/gilgoldzweig/EasyTabs/master/Mediafiles/image3.png" width="240" height="427">   <img style="user-select: none; cursor: zoom-in;" src="https://raw.githubusercontent.com/gilgoldzweig/EasyTabs/master/Mediafiles/image4.png" width="240" height="427">


Installing
-------------

**In your app's build.gradle add the following.**

    repositories {
    
    	maven {url "https://jitpack.io" }
	
	}
	
	dependencies {
		...
		compile 'com.github.gilgoldzweig:EasyTab:1.1.2'
	}


**In your xml add the easytabs view.**

       <goldzweigapps.tabs.View.EasyTabs
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/EasyTabs" />

**In your java file add the following.**
	
//Finding the EasyTabs view from our xml file
		
		EasyTabs tabs = (EasyTabs) findViewById(R.id.EasyTabs);
		
Creating a new builder for our tabs
		
		EasyTabsBuilder.with(tabs)
		
Adding the tabs by giving as much tab items as we want each tab item needs a fragment and a title the title can be a null.

		.addTabs(
			new TabItem(new frag1(), "Profile"), 
			new TabItem(new frag2(), "Camera"),
			new TabItem(new frag3(), "Favorite"),
			new TabItem(new frag4(), "Help"))
			
setting the tabs background color the function needs a int color.
	
			.setTabsBackgroundColor(EasyTabsColors.White)
			
setting the indicator color the function needs a int color.
			
			.setIndicatorColor(EasyTabsColors.Black)
			
Setting the text colors the first is when the tab is selected and the secound is when its not selected
	
			.setTextColors(EasyTabsColors.Black, EasyTabsColors.RoyalBlue) 
			
(optinal) Adding icons, the function need's the same amount of icons as in tabs you can put drawables or res id's int, the icons must be in size of 24dp on 24dp.
			
			.addIcons(
				R.drawable.ic_person_white_24dp,
				R.drawable.ic_photo_camera_white_24dp,
				R.drawable.ic_favorite_white_24dp,
				R.drawable.ic_help_white_24dp)
				
				
(optinal)Setting a custom Typeface for our text, in this case i selected the bubble.ttf which is in my assets diractory.
			
			
			.setCustomTypeface(Typeface.createFromAsset(getAssets(), "fonts/bubble.ttf"))
			
Adding a listener to keep track of the on screen position(optinal)
			
			.withListener(new TabsListener() {

			    @Override
			    public void onScreenPosition(int position) {
				Log.d("tag", String.valueOf(position));
			    }
			})
			
(optinal) Adding a icon fading the function fade all the icons that are not on screen and create a fade animation between to fragments like in facebook app.
	
			.setIconFading(true) 
			
(optinal) Hiding all titles so there will be only icons visable.
			
			.HideAllTitles(true) 
			
Building the tabs must be call last.
			
			.Build(); 



**To add tabs**

	addTabs(new TabItem(new fragment, "Tab title"));
	
**Tip** 

	You can add as many Tabitems as you want by separate them with **,** between each item.

----------


Available Transformation
-------------------
	A list of all available transformation.

	AccordionTransformer
	BackgroundToForegroundTransformer
	CubeInTransformer
	CubeOutTransformer
	DepthPageTransformer
	FlipHorizontalTransformer
	FlipVerticalTransformer
	ForegroundToBackgroundTransformer
	RotateDownTransformer
	RotateUpTransformer
	ScaleInOutTransformer
	StackTransformer
	TabletTransformer
	ZoomInTransformer
	ZoomOutSlideTransformer
	ZoomOutTranformer


Available features
-------------------

	addIcons(int... resid) 
	addIcons(Drawable... drawable) 
	addTransformation(boolean reverseDrawingOrder, ViewPager.PageTransformer transform)
	setIconFading(boolean fade)
	setIndicatorColor(@ColorInt int IndicatorColor)
	setBackgroundColor(@ColorInt int BackgroundColor)
	setTextColors(@ColorInt int selectedColor, @ColorInt int unselectedColor)
	setRTLPosition(boolean state)
	setCustomTypeface(final Typeface selected)
	WithListener(final TabsListener tabsListener)
	

  
  
  
EasyTabsColors
------
	EasyTabsColors is a java file filled with a lot of static colors for easy use so you wont need to search for the hex you want.

	If you want to use the colors in your layouts just copy the following to your colors file inside of values.
	
	<color name="White">#FFFFFF</color>
	<color name="Ivory">#FFFFF0</color>
	<color name="LightYellow">#FFFFE0</color>
	<color name="Yellow">#FFFF00</color>
	<color name="Snow">#FFFAFA</color>
	<color name="FloralWhite">#FFFAF0</color>
	<color name="LemonChiffon">#FFFACD</color>
	<color name="Cornsilk">#FFF8DC</color>
	<color name="Seashell">#FFF5EE</color>
	<color name="LavenderBlush">#FFF0F5</color>
	<color name="PapayaWhip">#FFEFD5</color>
	<color name="BlanchedAlmond">#FFEBCD</color>
	<color name="MistyRose">#FFE4E1</color>
	<color name="Bisque">#FFE4C4</color>
	<color name="Moccasin">#FFE4B5</color>
	<color name="NavajoWhite">#FFDEAD</color>
	<color name="PeachPuff">#FFDAB9</color>
	<color name="Gold">#FFD700</color>
	<color name="Pink">#FFC0CB</color>
	<color name="LightPink">#FFB6C1</color>
	<color name="Orange">#FFA500</color>
	<color name="LightSalmon">#FFA07A</color>
	<color name="DarkOrange">#FF8C00</color>
	<color name="Coral">#FF7F50</color>
	<color name="HotPink">#FF69B4</color>
	<color name="Tomato">#FF6347</color>
	<color name="OrangeRed">#FF4500</color>
	<color name="DeepPink">#FF1493</color>
	<color name="Fuchsia">#FF00FF</color>
	<color name="Magenta">#FF00FF</color>
	<color name="Red">#FF0000</color>
	<color name="OldLace">#FDF5E6</color>
	<color name="LightGoldenrodYellow">#FAFAD2</color>
	<color name="Linen">#FAF0E6</color>
	<color name="AntiqueWhite">#FAEBD7</color>
	<color name="Salmon">#FA8072</color>
	<color name="GhostWhite">#F8F8FF</color>
	<color name="MintCream">#F5FFFA</color>
	<color name="WhiteSmoke">#F5F5F5</color>
	<color name="Beige">#F5F5DC</color>
	<color name="Wheat">#F5DEB3</color>
	<color name="SandyBrown">#F4A460</color>
	<color name="Azure">#F0FFFF</color>
	<color name="Honeydew">#F0FFF0</color>
	<color name="AliceBlue">#F0F8FF</color>
	<color name="Khaki">#F0E68C</color>
	<color name="LightCoral">#F08080</color>
	<color name="PaleGoldenrod">#EEE8AA</color>
	<color name="Violet">#EE82EE</color>
	<color name="DarkSalmon">#E9967A</color>
	<color name="Lavender">#E6E6FA</color>
	<color name="LightCyan">#E0FFFF</color>
	<color name="BurlyWood">#DEB887</color>
	<color name="Plum">#DDA0DD</color>
	<color name="Gainsboro">#DCDCDC</color>
	<color name="Crimson">#DC143C</color>
	<color name="PaleVioletRed">#DB7093</color>
	<color name="Goldenrod">#DAA520</color>
	<color name="Orchid">#DA70D6</color>
	<color name="Thistle">#D8BFD8</color>
	<color name="LightGrey">#D3D3D3</color>
	<color name="Tan">#D2B48C</color>
	<color name="Chocolate">#D2691E</color>
	<color name="Peru">#CD853F</color>
	<color name="IndianRed">#CD5C5C</color>
	<color name="MediumVioletRed">#C71585</color>
	<color name="Silver">#C0C0C0</color>
	<color name="DarkKhaki">#BDB76B</color>
	<color name="RosyBrown">#BC8F8F</color>
	<color name="MediumOrchid">#BA55D3</color>
	<color name="DarkGoldenrod">#B8860B</color>
	<color name="FireBrick">#B22222</color>
	<color name="PowderBlue">#B0E0E6</color>
	<color name="LightSteelBlue">#B0C4DE</color>
	<color name="PaleTurquoise">#AFEEEE</color>
	<color name="GreenYellow">#ADFF2F</color>
	<color name="LightBlue">#ADD8E6</color>
	<color name="DarkGray">#A9A9A9</color>
	<color name="Brown">#A52A2A</color>
	<color name="Sienna">#A0522D</color>
	<color name="YellowGreen">#9ACD32</color>
	<color name="DarkOrchid">#9932CC</color>
	<color name="PaleGreen">#98FB98</color>
	<color name="DarkViolet">#9400D3</color>
	<color name="MediumPurple">#9370DB</color>
	<color name="LightGreen">#90EE90</color>
	<color name="DarkSeaGreen">#8FBC8F</color>
	<color name="SaddleBrown">#8B4513</color>
	<color name="DarkMagenta">#8B008B</color>
	<color name="DarkRed">#8B0000</color>
	<color name="BlueViolet">#8A2BE2</color>
	<color name="LightSkyBlue">#87CEFA</color>
	<color name="SkyBlue">#87CEEB</color>
	<color name="Gray">#808080</color>
	<color name="Olive">#808000</color>
	<color name="Purple">#800080</color>
	<color name="Maroon">#800000</color>
	<color name="Aquamarine">#7FFFD4</color>
	<color name="Chartreuse">#7FFF00</color>
	<color name="LawnGreen">#7CFC00</color>
	<color name="MediumSlateBlue">#7B68EE</color>
	<color name="LightSlateGray">#778899</color>
	<color name="SlateGray">#708090</color>
	<color name="OliveDrab">#6B8E23</color>
	<color name="SlateBlue">#6A5ACD</color>
	<color name="DimGray">#696969</color>
	<color name="MediumAquamarine">#66CDAA</color>
	<color name="CornflowerBlue">#6495ED</color>
	<color name="CadetBlue">#5F9EA0</color>
	<color name="DarkOliveGreen">#556B2F</color>
	<color name="Indigo">#4B0082</color>
	<color name="MediumTurquoise">#48D1CC</color>
	<color name="DarkSlateBlue">#483D8B</color>
	<color name="SteelBlue">#4682B4</color>
	<color name="RoyalBlue">#4169E1</color>
	<color name="Turquoise">#40E0D0</color>
	<color name="MediumSeaGreen">#3CB371</color>
	<color name="LimeGreen">#32CD32</color>
	<color name="DarkSlateGray">#2F4F4F</color>
	<color name="SeaGreen">#2E8B57</color>
	<color name="ForestGreen">#228B22</color>
	<color name="LightSeaGreen">#20B2AA</color>
	<color name="DodgerBlue">#1E90FF</color>
	<color name="MidnightBlue">#191970</color>
	<color name="Aqua">#00FFFF</color>
	<color name="Cyan">#00FFFF</color>
	<color name="SpringGreen">#00FF7F</color>
	<color name="Lime">#00FF00</color>
	<color name="MediumSpringGreen">#00FA9A</color>
	<color name="DarkTurquoise">#00CED1</color>
	<color name="DeepSkyBlue">#00BFFF</color>
	<color name="DarkCyan">#008B8B</color>
	<color name="Teal">#008080</color>
	<color name="Green">#008000</color>
	<color name="DarkGreen">#006400</color>
	<color name="Blue">#0000FF</color>
	<color name="MediumBlue">#0000CD</color>
	<color name="DarkBlue">#00008B</color>
	<color name="Navy">#000080</color>
	<color name="Black">#000000</color>


Creator
-------
	 Gil Goldzweig
	 goldzweigapps.tech
	 
Apps that using the library
---------------------------
	 EasyTabs.
	 Share my share.
	 
	 
	 
	 
	 
	 
	 If you're using the library please tell me so i can add you to the list.

Contact me
=======
	If you want to contribute to the library or get help send me an email and il answer as soon as possible.
 	Gil5841@gmail.com

