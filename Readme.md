


<h1> Model Code</h1>
<p>"
export default function App(){
  const [isModalVisible,setIsModalVisible] = useState(false);

  return (
  <View style = {{flex:1 , backgroundColor:"plum", padding:50}}>
      <Button
        title="Press Button"
        onPress={() => setIsModalVisible(true)}
        color="midnoghtblue"/>

        <Modal visible = {isModalVisible}
        onRequestClose={() => setIsModalVisible(false)}
        animationType="slide"
        presentationStyle="pagesheet">
      <View style = {{flex:1 , backgroundColor:"lightblue",padding:50}}>
        <Text>Modal Centent</Text>
        <Button title="Closed" color="midnightblue" 
        onPress={()=> setIsModalVisible(false)}/>
      </View>
      </Modal>

    </View>
    );
    } "
</p>


<h1>Status bar</h1>
<p>
    return (
    <View style = {{flex:1,backgroundColor:"plum", padding:50}}>
      <StatusBar backgroundColor="white" barStyle = "light-content" hidden/>
    </View>
  );
    
</p>

<h1> Activity Indicator </h1>
<h2>i.e. same like to page refresher loader </h2>

<p>

const logoImg = require("./assets/adaptive-icon.png");

export default function App(){
  const [IsLoadingIndicator, setIsLoadingIndicator] = useState(true);
  
  return (
    <View style = {{flex:1,backgroundColor:"plum", padding:50}}>
        <ActivityIndicator />
        <ActivityIndicator  size="large"/>
        <ActivityIndicator  size="large" color="midnightblue" animating={IsLoadingIndicator}/>
        <Button title="hide Loading" onPress={()=> setIsLoadingIndicator(!IsLoadingIndicator)}/>
    </View>
  );
}
</p>

<h1>Alert </h1>


<p>

export default function App(){
 
  
  return (
    <View style = {{flex:1,backgroundColor:"plum", padding:50}}>
      <Button title="Button" onPress={()=>Alert.alert("Invalid date")}/>
      <Button title="Button 2" onPress={()=>Alert.alert("Invalid date","DOB incorrect please Enter correct")}/>
      <Button title="Button 2" onPress={()=>Alert.alert("Invalid date","DOB incorrect please Enter correct",
    [
      {
        text:'Cancel',
        onPress: ()=> console.log('Cancel clicked'),
      },
      {
        text:'OK',
        onPress: ()=> console.log('Ok clicked'),
      }
    ])}/>
    </View>
  );
}

</p>

<h1>Custom Components </h1>

<h2>Greet.js</h2>

<p>


import { View,Text } from "react-native";

export default function Greet({name}){

    return (
        <View>
            <Text> Hello, {name}</Text>
        </View>
    );
    
}


export default function App(){
 
  return ( <View style = {{flex:1,backgroundColor:"white",padding:30}}>
        <Greet name='Lokesh Rao'/>
        <Greet name='Hitesh Yadav'/>
    </View>
  );
}
import { StatusBar } from "expo-status-bar";
import { useState } from "react";
import { ActivityIndicator } from "react-native";
import  Greet from "./components/Greet";

import { View,Alert, Text,Image,ImageBackground,ScrollView, Button,Pressable, Modal } from "react-native";




</p>

<h1> Stylesheet</h1>
<p>
import { View,Text,StyleSheet } from "react-native";

export default function App() {
  return (
    <View style = {styles.container}>

      <Text style = {styles.title}>StyleSheet API</Text>

    </View>
  );
}

const styles = StyleSheet.create({
  container:{ flex:1,padding:60,backgroundColor:"plum" },
  title:{textAlign:"center",fontWeight:"bold",fontSize:20}

})

</p>