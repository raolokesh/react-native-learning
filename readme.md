"#Readme2"

<h1> Relative and absolute Layout</h1>


<p>

export default function App() {
  return (
    // <View style={{backgroundColor:"plum",flex:1}}> </View>


    <View style={styles.container}>
      <Box style={{ backgroundColor: "black",alignSelf:"auto",flexShrink:1}} >Box 1-shrink</Box>
      <Box style={{ backgroundColor: "green" ,alignSelf:"auto",flexShrink:1}} >Box 2-shrink</Box>
      <Box style={{ backgroundColor: "lightgreen" ,alignSelf:"center",flexGrow:1}} >Box 3</Box>
      <Box style={{ backgroundColor: "plum" ,alignSelf:"stretch",flexBasis:150}} >Box 4</Box>
      <Box style={{ backgroundColor: "yellow" }} >Box 5</Box>
      <Box style={{ backgroundColor: "red" }} >Box 6</Box>
      <Box style={{ backgroundColor: "blue" }} >Box 7</Box>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    marginTop: 40,
    // height:400,
    margin: 10,
    borderWidth:10,
    borderColor:"red",
    // rowGap:20,
    // columnGap:20,
    gap:10,
    flexWrap:"auto",
    // alignContent: "center",
    flex: 1,
    alignItems:"flex-start",
    // justifyContent:"space-around",
    // flexDirection:"row",
  
  },
});
</p>
<h2> box.js</h2>
<p>
import { View,Text,StyleSheet } from "react-native";


export default function Box({ children, style }) {
    return (
    <View style = {[styles.box, style]}>
        <Text style = {styles.text}>{children}</Text>
    </View>
    );
}

const styles = StyleSheet.create({
    box:{
        backgroundColor:"white",
        padding:20,
        elevation:5,
        borderRadius:10,
        shadowColor:"lightskyblue",
        shadowRadius:20,
        height:100,
        width:100
    },
    text:{
        fontSize: 24,
        fontWeight:"bold",
        textAlign: "center",
        color:"white",
    }
});
</p>
