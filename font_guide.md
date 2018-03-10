## How to load custom fonts into your project (Expo). 

1) Download a custom font from the internet. [Font Squirrel](https://www.fontsquirrel.com) is a great resource for free fonts. 

2) Put the font files in a new folder called fonts with this path: 

`APP_NAME/assets/fonts/YOUR_FONT.ttf`

3) Import expo Font library into your component using expo's font. 

`import { Font } from 'expo'; `

4) Create a state object "fontLoaded" and set it to false. 

```
	this.state = {
      fontLoaded: false, 
    }; 
```

5) Too load the font, we use the Font library expo has provided us to to Asynchronously load the font in our `componentDidMountFunction()`

```
 async componentDidMount() {
 
    await Font.loadAsync({
      'open-sans-bold': require('../../assets/fonts/open-sans/OpenSans-Bold.ttf'),
    });

	//called after the font is loaded
    this.setState({ fontLoaded: true });
  }

```

6) Make a condition in your render function to make sure that the font is loaded only when the the state object `fontLoaded = true`

```
{ this.state.fontLoaded &&
	<Text style={{fontFamily: 'open-sans-bold'}}> My custom Font </Text>
}
```

