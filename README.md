# coffeetextview

[![](https://jitpack.io/v/devmike01/coffeetextview.svg)](https://jitpack.io/#devmike01/coffeetextview) [![Android Arsenal]( https://img.shields.io/badge/Android%20Arsenal-CoffeeTextView-green.svg?style=flat )]( https://android-arsenal.com/details/1/7086 )

A simple TextView library that lets developer easily set custom attributes through xml, programmatically or both

<img src="https://github.com/devmike01/coffeetextview/blob/master/coffeetextview/sample.gif" width="240" height="395" />

##### Step 1. Add the JitPack repository to your build file 
	allprojects {
		repositories {
			...
			maven { 
			url 'https://jitpack.io' 
			}
		}
	}
  
  ##### Step 2. Add the dependency
 	dependencies {
	        implementation 'com.github.devmike01:coffeetextview:v1.0.0'
	}
	
### Usage
Create an `Asset` folder. In the Asset folder, create another folder called `fonts`. Download and import font to the fonts folder you just created (Download free fonts here [1000freefonts](http://1001freefonts.com/) ). Create a new string resources and set the font's name including its extension(e.g .otf) as the value. Then use the string resource id in the `CoffeeTextView`. Also, you can use the animations and fonts that are already available in the library.

```xml
    <devmike.com.coffeetextview.CoffeeTextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:ct_caption_shadow_color="@color/colorAccent"
        app:ct_title_shadow_color="@color/colorPrimaryDark"
        app:ct_title_shadowDx="3"
        app:ct_title_typeface="@string/coffeefont_4"
        app:ct_caption_shadowDy="3"
        app:ct_title_animation="@anim/bounce_in"
        app:ct_title_shadowDy="3"
        app:ct_title_shadowRadius="1"
        app:ct_caption_shadowRadius="3"
        android:id="@+id/text_5"
        app:ct_caption_shadowDx="3"
        app:ct_title_size="12dp"
        app:ct_caption_color="@color/colorPrimaryDark"
        app:ct_caption_size="5dp"
        app:ct_caption_text="@string/app_name"
        app:ct_title_text="@string/app_name"/>
```

You can create an instance of `CoffeeTextView` in your kotlin or java file in order to set the textview properties programmatically.

### Kotlin sample

```kotlin
    private fun doAnimation(v :CoffeeTextView, anim :Int,  view :Button){
        val animation : Animation = v.animateCaption(anim)
        animation.duration =400
        v.animateTitle(anim)
        v.setCaptionText("Hello you click on: " + view.text.toString())
        v.setCaptionShadow(2f, 2f, 2f, Color.MAGENTA)
        v.setTitleColor(Color.RED)
        v.setTitleShadow(2f, 1f, 2f, Color.YELLOW)
    }
```
### Java Sample

```java
    private fun doAnimation(CoffeeTextView v, int anim,  Button view){
        Animation animation = v.animateCaption(anim)
        animation.setDuration(400)
        v.animateTitle(anim)
        v.setCaptionText("Hello you click on: " + view.text.toString())
        v.setCaptionShadow(2f, 2f, 2f, Color.MAGENTA)
        v.setTitleColor(Color.RED)
        v.setTitleShadow(2f, 1f, 2f, Color.YELLOW)
    }
```

### Licence
 Copyright [2018] [Oladipupo Gbenga]

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
limitations under the License.
