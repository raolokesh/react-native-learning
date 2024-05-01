"#Readme File" 

<h1> Dimension Api </h2>

<p> 

export default function App() {

  const [dimensions,setDimensions] = useState({
    window:Dimensions.get('window')

  });

  useEffect(() =>{
    const subscription = Dimensions.addEventListener("change",({window}) =>{
      setDimensions({window})
    });
    return () => subscription?.remove();
  });
  const {window} = dimensions;
  const windowWidth = window.width
  const windowHeight = window.height
  return (
    <View style={styles.container}>
        <View style = {[styles.box, {    width: windowWidth >500 ? "70%": "90%", height:windowHeight>600?"60%" :"90%"}]}>
          <Text style = {{fontSize: windowWidth >500? 50:24}}>Welcome! </Text>
        </View>
    </View>
  );
}
// const windowWidth = Dimensions.get("window").width
// const windowHeight = Dimensions.get("window").height

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
  box: {
    // width:windowWidth >500 ?"70%": "90%",
    // height:windowHeight>600?"60%" :"90%",
    backgroundColor:"lightblue",
    alignItems:"center",
    justifyContent: 'center',
  },
  // text:{
  //   fontSize:24,
  // }
});

</p>


<h1> useWindowDimensions </h1>
<h2> useWindowDimensions is recommended approach </h2>
<p>


export default function App() {

  const windowWidth = useWindowDimensions().width
  const windowHeight = useWindowDimensions().height

  return (
    <View style={styles.container}>
        <View style = {[styles.box, {    width: windowWidth >500 ? "70%": "90%", height:windowHeight>600?"60%" :"90%"}]}>
          <Text style = {{fontSize: windowWidth >500? 50:24}}>Welcome! </Text>
        </View>
    </View>
  );
}
// const windowWidth = Dimensions.get("window").width
// const windowHeight = Dimensions.get("window").height

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
  box: {
    // width:windowWidth >500 ?"70%": "90%",
    // height:windowHeight>600?"60%" :"90%",
    backgroundColor:"lightblue",
    alignItems:"center",
    justifyContent: 'center',
  },
  // text:{
  //   fontSize:24,
  // }
});


</p>

<h1> SafeAreaView </h1>

<p>


  return (
    <SafeAreaView style = {styles.safeContainer}>
    <View style={styles.container}>
        <View style = {styles.box}>
          <Text style = {styles.text}>Welcome! </Text>
        </View>
    </View>
    </SafeAreaView>
  );
}

const styles = StyleSheet.create({
  safeContainer:{
      flex: 1,
      backgroundColor:"plum"
  },
  container: {
    flex: 1,
    backgroundColor: 'plum',

  },
  box: {
  //  padding:20,
  },
  text:{
    fontSize:24,
    fontWeight: 'bold',
    textAlign: 'center',
  }
});

safe area that does not work
</p>


<h1> Platform specific code</h1>
<p>

import { StyleSheet, Text, View,SafeAreaView ,Platform } from 'react-native';
import CustomButton from './components/CustomButton/CustomButton';
export default function App() {



  return (
    <SafeAreaView style = {styles.safeContainer}>
    <View style={styles.container}>
        <View style = {styles.box}>
          <Text style = {styles.text}>Welcome! </Text>
          <CustomButton title = "Button" onPress={ () => alert("Button is pressed")}></CustomButton>
        </View>
    </View>
    </SafeAreaView>
  );
}

const styles = StyleSheet.create({
  safeContainer:{
      flex: 1,
      backgroundColor:"plum"
  },
  container: {
    flex: 1,
    backgroundColor: 'plum',
    paddingTop: Platform.OS ==="android" ? 25 :0,

  },
  box: {
  //  padding:20,
  },
  text:{
    ...Platform.select({
      ios:{
        color : "purple",
        fontSize: 34,
        fontStyle: "italic",
      },
      android:{
        color:"black",
        fontSize: 34,
        fontStyle: "italic",

      }
    }),
    fontWeight: 'bold',
    textAlign: 'center',
  }
});
</p>
<h2> in different file for different platforms</h2>
<p>
import React from "react";
import { Pressable,Text } from "react-native";

const CustomButton = ({onPress, title}) =>(
    <Pressable onPress={onPress}
    style = {{
        justifyContent: 'center',
        alignItems: 'center',
        backgroundColor: 'lightblue',
        borderRadius:5,
        padding:10
    }}>
        <Text style={{color:"blue",fontSize:18}}>{title}</Text>

    </Pressable>
);

export default CustomButton;

</p>


