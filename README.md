# react-native-css [![Circle CI](https://circleci.com/gh/sabeurthabti/react-native-css.svg?style=svg&circle-token=a140907997e6a37c6c5ec75f04e8150cef049ff6)](https://circleci.com/gh/sabeurthabti/react-native-css) [![NPM](https://img.shields.io/npm/dm/react-native-css.svg?style=flat-square)](https://www.npmjs.com/package/react-native-css)

> React-native-css turns valid CSS into the Facebook subset of CSS.

# News

## Version 2 
With version 2 come new changes:

- Remove sass/scss support, this is a huge overhead for little benefit. 
- No CLI, we believe that this is an unnecessary context switch
- NO I/O, no longer writing files, we do everything at runtime.  

## Install

Local

```bash
yarn add react-native-css --dev
```

```bash
npm install react-native-css --dev
```


# Example

Given the following CSS:

``` js
import reactNativeCSS from 'react-native-css';

reactNativeCSS(`
  description {
    margin-bottom: 20px;
    font-size: 18px;
    text-align: center;
    color: #656656;
  }

  container {
    padding: 30px;
    margin-top: 65px;
    align-items: center;
    display: block;
  }
`) 

```

React-native-css will generate to the following:

``` javascript
{"description":{"marginBottom":20,"fontSize":18,"textAlign":"center","color":"#656656"},"container":{"padding":30,"marginTop":65,"alignItems":"center"}}
```  
# Usage
```js
/import reactNativeCSS from 'react-native-css';



class SearchPage extends Component {
  render() {
    const { color, fontSize } = this.props;
      const styles = reactNativeCSS(`
        description {
          margin-bottom: 20px;
          font-size: ${fontSize}
          text-align: center;
          color: ${color}
        }

        container {
          padding: 30px;
          margin-top: 65px;
          align-items: center;
          display: block;
        }
      `) 

    return (
      <View style={styles.container}>
        <Text style={styles.description}>
            Search!
        </Text>
      </View>
    );
  }
}

```
