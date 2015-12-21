# react-native-iconic-font
Use iconic font in a simple way.

## Usage
### Notice:android library add custom font supports in v0.16,so make sure your native dependency is above it:  
`compile 'com.facebook.react:react-native:0.16.+'`

1. install module  
`npm install --save react-native-iconic-font`


	**setp 2 and 3 are same as offical way to use custom font.**  
2. copy font file 
	* font files are under `node_modules/react-native-iconic-font/fonts/`
	* just copy the file you want to use 
	* android:  
  copy file to `[project root]/android/app/src/main/assets/fonts/`
 	* ios:  
 	same as <https://github.com/oblador/react-native-vector-icons#option-manually>
 	
3. import to use  

```
var icon = require('react-native-iconic-font/font-awesome');

...

React.createClass({
  render: function() {
  //FontFamily perproty value must same as font file name.
    return (
       <Text style={{fontFamily: 'fontawesome-webfont',fontSize:30}}> 
                twitter-icon:{icon('twitter')}
       </Text>
    );
  }
});

```
reload js , you'll see the icon there.

##Icon Fonts
[Font-awesome](<http://fontawesome.io/>)  
[foundation-icons](<http://zurb.com/playground/foundation-icon-fonts-3>)  
[ionicons](<http://ionicons.com/>)  
[octicons](<https://github.com/github/octicons>)  
[typicons](<https://github.com/stephenhutchings/typicons.font>)  
[weathericons](<https://erikflowers.github.io/weather-icons/>)
[material-design-icons](<http://google.github.io/material-design-icons/>)
...  
   
**In fact,it will be so easy to use any iconic font after you read this article.**


## What's the difference?
There are already some good solutions to use iconic font :  
<https://github.com/oblador/react-native-vector-icons>   
<https://github.com/lwhiteley/react-native-android-iconify>  
<https://github.com/corymsmith/react-native-icons>  

**But** ... these libraries are all require native code and/or native project config file modifications.  
Believe me , it confusd many 'javascript' developers who are familar with 'native code'.  
That's why i start this project .  
**No native code. Let's try to use pure javascript!**

## How  
A font system is basically a 'character-graph' mapping.  
In a web page,CSS rules deal with webfont like this:

```
<i class="fa-twitter">
==CSS rules==> .fa-twitter:before{content: "\f099";} 
                                 ==font system==>  a twitter graph

```
It's same process in React native except the CSS rules.That's what this project do.**Mapping names to characters.**    
## Besides I create a command tool to help transforming CSS file to these mapping module. 
Run one command to generate the js module   
 `iconmap -f test/font-awesome-v4.4.0.css -p '^\.fa-([a-z0-9-]+?):before$'`  
Read more:  <https://github.com/sospartan/iconfont-map-builder> 


## Changelog
2015.11.24:
    * add material-design-icons
