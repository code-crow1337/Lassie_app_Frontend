# Lassie Application Frontend
Front-end part of the App for Lassie Company.
Created with React-Native with Expo, Typescript, React-Navigation as well Apollo.

The project lasted 4 weeks and involved both back-end and front-end technologies. The app will show the user dog information and as well related articles for helping 
the user to train their dog. 

The project was not completed in these 4 weeks, so for future implementation is the following:
AWS Auth with Google/Facebook
Save the data with Dynomitedb

## How to setup the project
1. Git clone ``` https://github.com/code-crow1337/Lassie_app_Frontend.git ```
2. Do a ```npm install ```
3. To fetch the dogs breeds and as well the articles from the backend.
   Follow the instruction in this [repo](https://github.com/code-crow1337/Lassie_app_Backend) and return here after the server is up. 
4. Do ```expo start ``` in the cmd.
5. Depending where you want to run the app on you need to do the following:
  - [Android](#set-up-for-android-studio-emulator)
  - [Mac](#setup-for-mac)
  - [Smartphone](#setup-physical-device)

### Set up for Android Studio Emulator 
[](#android)
1. Install Android Studio
2. Follow these instructions to create a [virtual Android device](https://docs.expo.io/workflow/android-studio-emulator/)
3. Start the virtual phone by clicking the green arrow icon in AVD Manager.
3. In the previous terminal where *Expo* is running. Keypress  ```a``` to run your app on your emulated android phone. 

### Setup for Mac
[](#ios)
1. To create a virtual IOS device follow these instructions [IOS simulation](https://docs.expo.io/workflow/ios-simulator/)
1. When running ```expo start ```  in the terminal. Keypress ```i``` to run it in your emulator. 

### Setup Physical Device
[](#app)
1. Go to Google Play or App Store and search for ```Expo```
2. In your terminal where Expo is running is a QR code which you can scan with your newly installed Expo app. 

## Troubleshooting
#### Articles are not showing/Breeds not showing
If you are running a virtual Android device you may not be able to fetch from the backend. Meaning a loading indicator keeps loading on the first screen.
You need to change set the specific IP-address to the backend. 

On Linux/BASH run in a separate command window:
```ifconfig ```
and use the IP-adress you get from enp30s0 and *inet* IP-address.
```paste``` that into App.tsx where we initiate the AppolloClient: 

``` 
const client = new ApolloClient({
  uri: 'http://<some IP adress>:4000',
  cache: new InMemoryCache(),
});
```

#### I'm not seeing the main app
The boolean value in the navigation needs to be changed to true.
In the ```navigation/index.tsx ``` there is an expression ```  const firstTime = false;```  set that to ```True``` and you will be redirected into
the main part of the app. 
