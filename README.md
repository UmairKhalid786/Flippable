<div align="center"><img src="https://user-images.githubusercontent.com/8867121/154110583-1e5364de-3106-47c7-9b94-bf8b1e9d6ff3.gif"/></div>
<h1 align="center">💳 Flippable</h1>
<h4 align="center">A Jetpack Compose utility library to create flipping Composable views with 2 sides.</h4>
<div align="center"><a href="https://twitter.com/intent/tweet?url=https%3A%2F%2Fgithub.com%2Fwajahatkarim3%2FEasyFlipViewPager&text=Create%20amazing%20book%20or%20card%20flipping%20animations%20for%20your%20ViewPager%20in%20Android%20with%20these%202-lines%20of%20code%20through%20EasyFlipViewPager&hashtags=android%2C%20kotlin%2C%20java%2C%20opensource%2C%20programming">
        <img src="https://img.shields.io/twitter/url/http/shields.io.svg?style=social"/>
    </a> <a href="https://twitter.com/WajahatKarim">
        <img src="https://img.shields.io/twitter/follow/WajahatKarim?style=social"/>
    </a>
</div> 
<br/>


<div align="center">
  <img src="https://img.shields.io/maven-central/v/com.wajahatkarim/flippable" />
    <!-- PRs Welcome -->
    <a href="">
        <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg"/>
    </a>
    <!-- Say Thanks! -->
    <a href="https://saythanks.io/to/wajahatkarim3">
        <img src="https://img.shields.io/badge/Say%20Thanks-!-1EAEDB.svg"/>
    </a>
    <a href="https://www.paypal.me/WajahatKarim/5">
        <img src="https://img.shields.io/badge/$-donate-ff69b4.svg?maxAge=2592000&amp;style=flat">
    </a>
</div>

<div align="center">
  <sub>Built with ❤︎ by
  <a href="https://twitter.com/WajahatKarim">Wajahat Karim</a> and
  <a href="https://github.com/wajahatkarim3/Flippable/graphs/contributors">
    contributors
  </a>
</div>
<br/>
<br/>

## Demo
https://user-images.githubusercontent.com/8867121/154115910-8e2d2661-97c0-4b5a-b27e-76857533afe6.mp4
              
<br/>
<br/>
        
## 💻 Installation
In `build.gradle` of `app` module, include this dependency
        
```groovy
implementation "com.wajahatkarim:flippable:x.y.z"
```
        
Please replace x, y and z with the latest version numbers ![](https://img.shields.io/maven-central/v/com.wajahatkarim/flippable).
        
Or you can find latest version and changelogs in the [releases](https://github.com/wajahatkarim3/Flippable/releases).

<br/>
        
## ❓ Usage

Add the [`Flippable`](https://github.com/wajahatkarim3/Flippable/blob/main/flippable/src/main/java/com/wajahatkarim/flippable/Flippable.kt) composable and define the front and back side composable methods inside. That's it.

```kotlin
Flippable(
    frontSide = {
        // Composable content for the front side
    },

    backSide = {
        // Composable content for the back side
    },

    flipController = rememberFlipController(),

    // Other optional parameters
)
```
    
<br/>
    
## 🎨 Customization Parameters
If you'd like to discover what `Flippable` offers, here is an exhaustive description of customizable parameters.
    
```kotlin
    
val controller = rememberFlipController()
    
Flippable(
    frontSide = {
        // Composable content for the front side
    },
    
    backSide = {
        // Composable content for the back side
    },
    
    // To manually controll the flipping, you would need an instance of FlippableController. 
    // You can access it using rememberFlipController() method.
    // This provides methods like controller.flip(), controller.flipToFront(), controller.flipToBack() etc.
    flipController = controller,
    
    // The obvious one - if you have done Jetpack Compose before.
    modifier = Modifier,
    
    // The duration it takes for the flip transition in Milliseconds. Default is 400
    flipDurationMs = 400,
    
    // If true, this will flip the view when touched. 
    // If you want to programatically flip the view without touching, use FlippableController.
    flipOnTouch = flipOnTouchEnabled,
    
    // If false, flipping will be disabled completely. 
    // The flipping will not be triggered with either touch or with controller methods.
    flipEnabled = flipEnabled,
    
    // The Flippable is contained in a Box, so this tells
    // the alignment to organize both Front and Back side composable.
    contentAlignment = Alignment.TopCenter,
    
    //If true, the Flippable will automatically flip back after 
    //duration defined in autoFlipDurationMs. By default, this is false..
    autoFlip = false,
    
    //The duration in Milliseconds after which auto-flip back animation will start. Default is 1 second.
    autoFlipDurationMs = 1000,
    
    // The animation type of flipping effect. Currently there are 4 animations. 
    // Horizontal Clockwise and Anti-Clockwise, Vertical Clockwise and Anti-Clockwise
    // See animation types section below.
    flipAnimationType = FlipAnimationType.HORIZONTAL_CLOCKWISE,
    
    // The [GraphicsLayerScope.cameraDistance] for the flip animation. 
    // Sets the distance along the Z axis (orthogonal to the X/Y plane
    // on which layers are drawn) from the camera to this layer.
    cameraDistance = 30.0F,
    
    // The listener which is triggered when flipping animation is finished.
    onFlippedListener = { currentSide ->
        // This is called when any flip animation is finished. 
        // This gives the current side which is visible now in Flippable.
    }
)
```
