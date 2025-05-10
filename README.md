## 📘 **React Native Syllabus: Beginner to Advanced**

### 🟢 **Beginner Level**

#### 1. **Introduction to React Native**

* What is React Native?
* Differences between React and React Native
* How React Native works (Bridge concept)
* Setting up development environment (Expo CLI & React Native CLI)
* Android/iOS Emulator setup

#### 2. **Basic Components**

* `View`, `Text`, `Image`, `ScrollView`, `TextInput`
* `Button`, `TouchableOpacity`, `TouchableHighlight`
* `SafeAreaView`, `StatusBar`

#### 3. **Styling in React Native**

* Flexbox layout
* Stylesheet API
* Responsive design
* Platform-specific styling

#### 4. **React Fundamentals**

* JSX
* Functional Components
* Props and State
* Handling user input & events

#### 5. **Navigation**

* Introduction to React Navigation
* Stack Navigator
* Bottom Tab Navigator
* Drawer Navigator
* Passing data between screens

---

### 🟡 **Intermediate Level**

#### 6. **State Management**

* React Context API
* Redux Basics
* Redux Toolkit
* Async actions with Redux Thunk

#### 7. **Forms & Validation**

* Controlled vs uncontrolled components
* Form libraries: Formik, React Hook Form
* Validation using Yup

#### 8. **Networking**

* Fetch API
* Axios for HTTP requests
* Working with REST APIs
* Error handling and loaders

#### 9. **Persistent Storage**

* AsyncStorage
* MMKV or Realm for secure and faster storage
* SecureStore (for storing sensitive data)

#### 10. **Device Features & APIs**

* Camera (expo-camera or react-native-camera)
* Location
* Permissions
* Push Notifications (Expo Notifications or Firebase)
* Deep Linking

#### 11. **Custom Components & Reusability**

* Creating reusable UI components
* Component composition
* Conditional rendering
* FlatList and SectionList

---

### 🔴 **Advanced Level**

#### 12. **Performance Optimization**

* Memoization: `React.memo`, `useMemo`, `useCallback`
* Lazy loading components
* FlatList optimization
* Removing unnecessary re-renders
* Avoiding memory leaks

#### 13. **Advanced Navigation**

* Custom transitions
* Deep linking
* Nested navigators
* Authentication flow (public vs private routes)

#### 14. **Animations**

* LayoutAnimation and Animated API
* Reanimated 2
* Gesture Handler integration
* Building complex UI interactions

#### 15. **Testing**

* Unit Testing with Jest
* Component testing with React Native Testing Library
* Snapshot testing
* Mocking API calls

#### 16. **TypeScript with React Native**

* Setting up TypeScript
* Typing props, state, and navigation
* Type-safe Redux & API responses

#### 17. **Authentication & Security**

* Firebase Auth / OAuth providers
* Token-based auth (JWT)
* Secure storage
* Biometric authentication

#### 18. **CI/CD & App Deployment**

* Android & iOS builds (APK, AAB, IPA)
* App Store / Play Store submission
* Code signing, certificates & profiles
* Using EAS (Expo Application Services)
* CI/CD with GitHub Actions, Bitrise, or Fastlane

#### 19. **Monorepos & Modularization (Optional)**

* Lerna or Nx with React Native
* Managing shared components and services

#### 20. **Advanced Libraries & Ecosystem**

* react-query / tanstack-query
* Zustand, Jotai, or Recoil
* Detox for end-to-end testing
* Storybook for component development

---

### 🧠 **Capstone Projects**

* To-do App (Beginner)
* News Reader App with API integration (Intermediate)
* Chat App with Firebase (Intermediate-Advanced)
* E-commerce App with Authentication, Cart, and Checkout (Advanced)
* Fitness Tracker with animations, charts, and local storage (Advanced)


Here’s a neatly structured **section titled “1. Introduction to React Native”** covering all the points you listed:

---

## 📱 1. **Introduction to React Native**

### 🧾 What is React Native?

React Native is an open-source framework developed by **Meta (Facebook)** that allows developers to build **cross-platform mobile applications** using **JavaScript** and **React**.

* **Write once, deploy to both Android and iOS.**
* Uses **native components** instead of web views.
* Enables a rich, performance-optimized user experience with **a single codebase**.

---

### 🔄 Differences between React and React Native

| Feature                      | React (Web)                      | React Native (Mobile)                  |
| ---------------------------- | -------------------------------- | -------------------------------------- |
| Platform                     | Web browsers                     | iOS and Android                        |
| UI Components                | HTML tags (`<div>`, `<p>`, etc.) | Native components (`<View>`, `<Text>`) |
| Styling                      | CSS, SASS, styled-components     | StyleSheet API (CSS-in-JS syntax)      |
| Navigation                   | React Router                     | React Navigation                       |
| Rendering Engine             | DOM                              | Native views rendered via Bridge       |
| Accessibility to Native APIs | Not direct                       | Via Native Modules / Bridge            |

---

### 🧠 How React Native Works (Bridge Concept)

React Native uses a **"bridge"** to facilitate communication between **JavaScript code** and the **native platform APIs**.

#### Architecture:

1. **JavaScript Thread**: Executes app logic written in JS.
2. **Bridge**: Acts as a communication layer between JS and native modules.
3. **Native Thread**: Executes platform-specific code (UI, camera, sensors, etc.).

#### ⚙️ Flow:

* You write UI and logic in JavaScript.
* Commands/data are passed to native modules through the Bridge.
* The native UI is updated, and any response is sent back via the Bridge.

> 🧩 New architecture (Fabric & TurboModules) reduces overhead and improves performance by making calls synchronous where possible.

---

### ⚙️ Setting Up Development Environment

#### 🟢 Option 1: **Expo CLI** (Beginner-Friendly)

* No native code setup required
* Great for fast prototyping and testing

**Steps:**

```bash
npm install -g expo-cli
expo init MyApp
cd MyApp
npm start
```

**Run on:**

* Expo Go app (on physical device)
* Android/iOS Emulator (if available)

#### 🟠 Option 2: **React Native CLI** (Advanced/Custom Native Code)

* Allows full native module integration
* Best for apps with custom native functionality

**Steps:**

```bash
npx react-native init MyApp
cd MyApp
npx react-native run-android
npx react-native run-ios  # macOS only
```

> Requires Android Studio & Xcode setup

---

### 📱 Android/iOS Emulator Setup

#### Android:

1. Install **Android Studio**.
2. Open SDK Manager > Install latest Android SDK.
3. Open AVD Manager > Create new virtual device.
4. Start emulator and run:

   ```bash
   npx react-native run-android
   ```

#### iOS (macOS only):

1. Install **Xcode** from App Store.
2. Open Xcode > Preferences > Install command line tools.
3. Use iOS Simulator:

   ```bash
   npx react-native run-ios
   ```

Here’s a well-organized explanation for:

---

## 📦 2. **Basic Components in React Native**

React Native provides a core set of UI components for building native interfaces. Below are the most commonly used components grouped by functionality.

---

### 🧱 **Layout & Display Components**

#### 🔹 `View`

* Equivalent of a `div` in web.
* Acts as a container for other components.

```tsx
<View style={{ padding: 20, backgroundColor: 'lightgray' }}>
  <Text>Hello World</Text>
</View>
```

---

#### 🔹 `Text`

* Used to display text.
* Supports nesting and styling.

```tsx
<Text style={{ fontSize: 20 }}>Welcome to React Native</Text>
```

---

#### 🔹 `Image`

* Displays images from local assets or remote URLs.

```tsx
<Image source={{ uri: 'https://example.com/logo.png' }} style={{ width: 100, height: 100 }} />
```

---

#### 🔹 `ScrollView`

* A scrollable container useful for wrapping content that exceeds the screen height.

```tsx
<ScrollView>
  <Text>Long content goes here...</Text>
</ScrollView>
```

---

#### 🔹 `TextInput`

* Accepts user input (like input fields in HTML).

```tsx
<TextInput 
  placeholder="Enter your name" 
  style={{ borderBottomWidth: 1, padding: 8 }} 
/>
```

---

### 🧲 **Interactivity Components**

#### 🔹 `Button`

* Simple button component with basic props.

```tsx
<Button title="Press Me" onPress={() => alert('Pressed!')} />
```

> Limitation: Not very customizable.

---

#### 🔹 `TouchableOpacity`

* Makes any element tappable and fades on press.

```tsx
<TouchableOpacity onPress={() => alert('Pressed!')}>
  <Text>Tap Me</Text>
</TouchableOpacity>
```

---

#### 🔹 `TouchableHighlight`

* Similar to `TouchableOpacity`, but gives a “highlight” background on press.

```tsx
<TouchableHighlight 
  onPress={() => alert('Pressed!')} 
  underlayColor="lightgray"
>
  <Text>Highlight Me</Text>
</TouchableHighlight>
```

---

### 📱 **Safe Area & UI Meta Components**

#### 🔹 `SafeAreaView`

* Ensures content doesn't overlap system UI (e.g. notch, home indicator).

```tsx
<SafeAreaView style={{ flex: 1 }}>
  <Text>Content within safe area</Text>
</SafeAreaView>
```

---

#### 🔹 `StatusBar`

* Allows customization of the top status bar (color, style, visibility).

```tsx
<StatusBar barStyle="dark-content" backgroundColor="#fff" />
```

Here’s a comprehensive breakdown of **styling in React Native**:

---

## 🖌️ 3. **Styling in React Native**

React Native uses a **flexible** and **native** approach to styling components. The styles are written in **JavaScript** using the **StyleSheet API**, and React Native follows the **Flexbox layout model** for positioning and alignment.

---

### 📐 **Flexbox Layout in React Native**

Flexbox is the primary layout system in React Native. It allows you to design complex layouts in a **1D axis** (row or column).

#### Main Properties:

* **`flexDirection`**: Defines the direction of the layout (row or column).
* **`justifyContent`**: Aligns children components along the main axis (horizontal/vertical).
* **`alignItems`**: Aligns children components along the cross axis (perpendicular to the main axis).
* **`flex`**: Defines how a component grows relative to others in the layout.

#### Example:

```tsx
<View style={{ flexDirection: 'row', justifyContent: 'space-between', alignItems: 'center' }}>
  <Text>Item 1</Text>
  <Text>Item 2</Text>
  <Text>Item 3</Text>
</View>
```

> **Explanation**:

* `flexDirection: 'row'` arranges children horizontally.
* `justifyContent: 'space-between'` distributes the space evenly.
* `alignItems: 'center'` aligns the items vertically in the middle.

---

### 🖥️ **Stylesheet API**

React Native uses **`StyleSheet`** for creating styles. This is more performant compared to inline styles since it reduces unnecessary re-renders.

#### Creating Styles:

```tsx
import { StyleSheet, Text, View } from 'react-native';

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#fff',
  },
  text: {
    fontSize: 20,
    color: 'blue',
  },
});

const MyComponent = () => (
  <View style={styles.container}>
    <Text style={styles.text}>Hello, React Native!</Text>
  </View>
);
```

#### Key Styling Properties:

* **Positioning**: `position`, `top`, `right`, `bottom`, `left`
* **Spacing**: `margin`, `padding`, `gap`
* **Size**: `width`, `height`
* **Typography**: `fontFamily`, `fontSize`, `fontWeight`
* **Colors**: `backgroundColor`, `color`, `borderColor`

---

### 📱 **Responsive Design in React Native**

Unlike web development, React Native doesn’t have media queries. To make your app responsive, you can use the **`Dimensions` API** or libraries like **`react-native-responsive-dimensions`**.

#### Using the `Dimensions` API:

```tsx
import { Dimensions, Text, View } from 'react-native';

const { width, height } = Dimensions.get('window');

const App = () => (
  <View style={{ padding: 20, backgroundColor: width > 500 ? 'lightblue' : 'lightcoral' }}>
    <Text style={{ fontSize: width > 500 ? 24 : 16 }}>Responsive Text</Text>
  </View>
);
```

> This adjusts the layout based on the device's width.

#### Media Queries with Libraries:

You can use libraries like **`react-native-responsive-screen`** or **`react-native-responsive-dimensions`** to scale UI elements based on screen size.

---

### 🖼️ **Platform-Specific Styling**

React Native allows you to apply platform-specific styles using **`Platform`** module or **`Platform.select()`** method. This is particularly useful when you want to adjust styles for **iOS** vs. **Android**.

#### Example:

```tsx
import { Platform, StyleSheet, Text, View } from 'react-native';

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: Platform.OS === 'ios' ? 'lightblue' : 'lightgreen',
  },
  text: {
    fontSize: Platform.select({ ios: 20, android: 18 }),
  },
});

const App = () => (
  <View style={styles.container}>
    <Text style={styles.text}>Platform-specific Styling</Text>
  </View>
);
```

> **Explanation**:

* The `Platform.OS` is used to check the current platform (iOS or Android).
* `Platform.select()` allows you to specify different values based on the platform.

---

### 🖍️ **Best Practices for Styling**

1. **Use `StyleSheet.create()`**: This improves performance by reducing re-renders.
2. **Avoid inline styles for frequently updated components**: Use `useMemo` for complex styles to prevent recalculating them.
3. **Keep components modular**: Create smaller, reusable styles for better maintainability.
4. **Optimize for small screens**: Ensure that your UI adapts well to both small and large screen sizes.

---

Here’s a structured overview of **React Fundamentals**:

---

## ⚙️ 4. **React Fundamentals**

Understanding React is essential for building dynamic user interfaces. This section covers key React concepts, from JSX to handling user input and events.

---

### 📝 **JSX (JavaScript XML)**

JSX is a **syntax extension** for JavaScript, used to describe what the UI should look like. It’s not required in React, but it’s widely used because it looks similar to HTML, making it more intuitive for developers.

#### Key Points:

* JSX gets **transformed** into `React.createElement()` calls by Babel.
* Allows embedding JavaScript expressions inside HTML-like code using `{}`.

#### Example:

```tsx
const greeting = "Hello, React!";
const element = <h1>{greeting}</h1>;  // JSX syntax

ReactDOM.render(element, document.getElementById('root'));
```

> **Note**: JSX is **not HTML**, but it looks similar. For example, in JSX, `class` becomes `className` and `for` becomes `htmlFor`.

---

### 🧑‍💻 **Functional Components**

A functional component is a **JavaScript function** that returns a **JSX element**. Functional components are simpler and focus on receiving **props** and rendering the UI.

#### Example:

```tsx
const Welcome = (props: { name: string }) => {
  return <h1>Hello, {props.name}!</h1>;
};
```

* **Props** are passed into a component to render dynamic data.

#### Using the component:

```tsx
<Welcome name="John" />
```

---

### 🧑‍🤝‍🧑 **Props and State**

#### 🔹 **Props**

* **Props** (short for "properties") allow passing data from a parent component to a child component.
* Props are **read-only** and cannot be modified by the child component.

#### Example:

```tsx
const Greeting = (props: { name: string }) => {
  return <h1>Hello, {props.name}!</h1>;
};

const ParentComponent = () => {
  return <Greeting name="Alice" />;
};
```

* The `name` prop is passed from `ParentComponent` to `Greeting`.

#### 🔹 **State**

* **State** is data that is specific to the component and can change over time.
* Unlike props, **state** can be modified within the component using **`useState`** in functional components.

#### Example using `useState`:

```tsx
import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);  // Declare a state variable and its updater function

  const increment = () => setCount(count + 1);

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={increment}>Increment</button>
    </div>
  );
};
```

* **State** is mutable, and the component will re-render when the state changes.

---

### 🎮 **Handling User Input & Events**

React allows you to handle user input and events through **event handlers**. These handlers can be attached to JSX elements and can capture user actions like clicks, form submissions, or text input.

#### 🔹 **Event Handlers**

Event handlers in React are written in camelCase and are passed as functions to JSX elements.

```tsx
const ClickButton = () => {
  const handleClick = () => {
    alert("Button clicked!");
  };

  return <button onClick={handleClick}>Click Me</button>;
};
```

> **Explanation**:

* `onClick` is a React event handler that listens for a click event. When the button is clicked, it triggers the `handleClick` function.

#### 🔹 **Handling Form Input**

React makes handling form inputs easy with controlled components, where form data is handled by the React state.

```tsx
const NameForm = () => {
  const [name, setName] = useState("");

  const handleChange = (event: React.ChangeEvent<HTMLInputElement>) => {
    setName(event.target.value);
  };

  const handleSubmit = (event: React.FormEvent) => {
    event.preventDefault();
    alert("Form submitted: " + name);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="text"
        value={name}
        onChange={handleChange}
        placeholder="Enter your name"
      />
      <button type="submit">Submit</button>
    </form>
  );
};
```

* `value` prop makes it a **controlled component**, linking the form input to React's state.
* `onChange` is triggered whenever the user types in the input field.

---

### 📜 **Summary**

* **JSX** allows us to write HTML-like code within JavaScript.
* **Functional components** are simple JavaScript functions that return JSX.
* **Props** are used to pass data down to child components (read-only).
* **State** is local, mutable data used to manage the component's behavior or UI.
* **Event handlers** in React are used to handle user actions such as clicks or form submissions.

---

Here’s an organized guide to **Navigation in React Native** using **React Navigation**:

---

## 🚀 5. **Navigation in React Native**

React Navigation is the most popular library for implementing navigation in React Native apps. It provides various navigators like **Stack**, **Tab**, and **Drawer** to help you build a seamless app with multiple screens.

---

### 🗺️ **Introduction to React Navigation**

React Navigation is a fully customizable navigation library for React Native. It helps you navigate between different screens in your app using **navigators**. The main types of navigators are:

1. **Stack Navigator** - Navigates between screens in a stack (like a stack of cards).
2. **Bottom Tab Navigator** - Displays a tab bar at the bottom of the screen for navigation.
3. **Drawer Navigator** - Displays a side menu or drawer for navigation.

#### Installation:

To start using React Navigation, install the following dependencies:

```bash
npm install @react-navigation/native
npm install react-native-screens react-native-safe-area-context
```

For **stack navigation** and others, you'll also need:

```bash
npm install @react-navigation/stack
npm install @react-navigation/bottom-tabs
npm install @react-navigation/drawer
```

> Make sure to follow installation instructions for setting up in **Android** and **iOS** from the React Navigation documentation for proper linking and configuration.

---

### 📚 **Stack Navigator**

The **Stack Navigator** allows you to push and pop screens, much like how a stack works, making it ideal for flows like login screens or navigation hierarchies.

#### Example:

```tsx
import React from 'react';
import { createStackNavigator } from '@react-navigation/stack';
import { NavigationContainer } from '@react-navigation/native';
import HomeScreen from './HomeScreen';
import DetailsScreen from './DetailsScreen';

const Stack = createStackNavigator();

const App = () => (
  <NavigationContainer>
    <Stack.Navigator initialRouteName="Home">
      <Stack.Screen name="Home" component={HomeScreen} />
      <Stack.Screen name="Details" component={DetailsScreen} />
    </Stack.Navigator>
  </NavigationContainer>
);

export default App;
```

* **Navigation** between screens is handled by the `Stack.Navigator`.
* The `initialRouteName` prop defines which screen is shown first.

---

### ⬇️ **Bottom Tab Navigator**

A **Bottom Tab Navigator** shows a bottom navigation bar with tabs, which is commonly used for switching between top-level views (e.g., Home, Settings, Profile).

#### Example:

```tsx
import React from 'react';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';
import { NavigationContainer } from '@react-navigation/native';
import HomeScreen from './HomeScreen';
import SettingsScreen from './SettingsScreen';

const Tab = createBottomTabNavigator();

const App = () => (
  <NavigationContainer>
    <Tab.Navigator>
      <Tab.Screen name="Home" component={HomeScreen} />
      <Tab.Screen name="Settings" component={SettingsScreen} />
    </Tab.Navigator>
  </NavigationContainer>
);

export default App;
```

> **Key Points**: Bottom tabs are great for static navigation, where each tab is associated with a high-level feature.

---

### 🧑‍💼 **Drawer Navigator**

The **Drawer Navigator** is a side menu that slides in from the left (or right) of the screen. It’s useful for apps with a lot of options or sections.

#### Example:

```tsx
import React from 'react';
import { createDrawerNavigator } from '@react-navigation/drawer';
import { NavigationContainer } from '@react-navigation/native';
import HomeScreen from './HomeScreen';
import SettingsScreen from './SettingsScreen';

const Drawer = createDrawerNavigator();

const App = () => (
  <NavigationContainer>
    <Drawer.Navigator initialRouteName="Home">
      <Drawer.Screen name="Home" component={HomeScreen} />
      <Drawer.Screen name="Settings" component={SettingsScreen} />
    </Drawer.Navigator>
  </NavigationContainer>
);

export default App;
```

* **Drawer.Navigator** creates a side menu with different screens.
* You can customize the drawer (position, content) and add various screen options.

---

### 🛠️ **Passing Data Between Screens**

In React Navigation, you can pass data between screens using **params** and **navigation** object.

#### **Passing Params to Another Screen**

You can pass data (params) to a screen when navigating to it.

```tsx
// From HomeScreen
navigation.navigate('Details', { userId: 42 });

// In the DetailsScreen
const DetailsScreen = ({ route }) => {
  const { userId } = route.params;
  return <Text>User ID: {userId}</Text>;
};
```

#### **Accessing Params in the Target Screen**

* `route.params` is where you access the passed parameters.
* You can pass any type of data (strings, objects, arrays).

---

### 🗣️ **Navigation Methods**

Some commonly used navigation methods:

* `navigate('ScreenName')`: Navigate to another screen.
* `goBack()`: Go back to the previous screen.
* `push('ScreenName')`: Push a new screen on top of the stack.
* `reset()`: Reset the navigation stack (useful for after login).

---

### 📱 **Example: Full Navigation Setup**

```tsx
import React from 'react';
import { Button, Text, View } from 'react-native';
import { createStackNavigator } from '@react-navigation/stack';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';
import { NavigationContainer } from '@react-navigation/native';

const Stack = createStackNavigator();
const Tab = createBottomTabNavigator();

const HomeScreen = ({ navigation }) => (
  <View>
    <Text>Home Screen</Text>
    <Button
      title="Go to Details"
      onPress={() => navigation.navigate('Details', { userId: 42 })}
    />
  </View>
);

const DetailsScreen = ({ route }) => (
  <View>
    <Text>Details Screen</Text>
    <Text>User ID: {route.params.userId}</Text>
  </View>
);

const SettingsScreen = () => <Text>Settings Screen</Text>;

const TabNavigator = () => (
  <Tab.Navigator>
    <Tab.Screen name="Home" component={HomeScreen} />
    <Tab.Screen name="Settings" component={SettingsScreen} />
  </Tab.Navigator>
);

const App = () => (
  <NavigationContainer>
    <Stack.Navigator initialRouteName="Home">
      <Stack.Screen name="Home" component={TabNavigator} />
      <Stack.Screen name="Details" component={DetailsScreen} />
    </Stack.Navigator>
  </NavigationContainer>
);

export default App;
```

---

### 📚 **Summary**

* **Stack Navigator**: Ideal for hierarchical navigation (e.g., Login -> Dashboard).
* **Bottom Tab Navigator**: Great for top-level navigation between core features.
* **Drawer Navigator**: Useful for apps with many sections, displaying a menu.
* **Passing data**: You can pass data between screens using **params** via `navigation.navigate()`.

---

Here’s a detailed breakdown of **State Management** at the intermediate level, focusing on **React Context API**, **Redux**, and **Redux Toolkit**, along with **Async actions using Redux Thunk**:

---

## 🟡 **6. State Management**

State management is crucial for managing and controlling the flow of data in an app, especially in complex applications. **React Context API** and **Redux** are two popular solutions for handling state in React.

---

### 🔲 **React Context API**

The **React Context API** is a simpler, built-in solution to manage global state without the need for a third-party library like Redux. It is useful for smaller applications or when you need to share state across multiple components.

#### Key Concepts:

* **Provider**: A component that makes the state available to the components within its scope.
* **Consumer**: A component that subscribes to the context and gets access to the state.
* **useContext()**: A React hook that allows components to access context values.

#### Example:

```tsx
import React, { createContext, useState, useContext } from 'react';

// 1. Create a Context
const UserContext = createContext(null);

const UserProvider = ({ children }) => {
  const [user, setUser] = useState(null);

  const login = (userData) => setUser(userData);
  const logout = () => setUser(null);

  return (
    <UserContext.Provider value={{ user, login, logout }}>
      {children}
    </UserContext.Provider>
  );
};

const UserProfile = () => {
  const { user, logout } = useContext(UserContext);
  
  return (
    <div>
      {user ? (
        <div>
          <h2>{user.name}</h2>
          <button onClick={logout}>Logout</button>
        </div>
      ) : (
        <h2>Please log in</h2>
      )}
    </div>
  );
};

const App = () => (
  <UserProvider>
    <UserProfile />
  </UserProvider>
);

export default App;
```

* **`UserContext.Provider`** wraps the app and provides the `user` and `login`/`logout` methods to the components.
* **`useContext(UserContext)`** is used to consume the context in the `UserProfile` component.

---

### 🔴 **Redux Basics**

**Redux** is a predictable state container for JavaScript apps. It helps manage application state in a centralized store, making state management predictable and easier to debug.

#### Key Concepts:

1. **Actions**: Payloads of information that send data from the app to the Redux store.
2. **Reducers**: Functions that specify how the state changes in response to an action.
3. **Store**: The centralized state of the app.
4. **Dispatch**: A function used to send actions to the Redux store.

#### Steps to use Redux:

1. **Define Actions**
2. **Create Reducers**
3. **Create the Store**
4. **Dispatch Actions**

#### Example:

```tsx
import { createStore } from 'redux';

// 1. Action
const INCREMENT = 'INCREMENT';

const increment = () => ({ type: INCREMENT });

// 2. Reducer
const counterReducer = (state = { count: 0 }, action) => {
  switch (action.type) {
    case INCREMENT:
      return { count: state.count + 1 };
    default:
      return state;
  }
};

// 3. Store
const store = createStore(counterReducer);

// 4. Dispatch action
store.dispatch(increment());
console.log(store.getState()); // { count: 1 }
```

* Actions are dispatched to the store.
* Reducers update the state based on the action type.
* The store holds the entire app's state.

---

### 🟢 **Redux Toolkit**

**Redux Toolkit** simplifies working with Redux by providing pre-configured functions and utilities for common tasks (e.g., creating reducers, defining actions, handling async actions).

#### Key Features:

* **`createSlice`**: Automatically generates actions and reducers.
* **`configureStore`**: Simplifies store setup with Redux DevTools support.
* **`createAsyncThunk`**: Allows handling async actions (e.g., fetching data from APIs).

#### Example using Redux Toolkit:

```tsx
import { createSlice, configureStore } from '@reduxjs/toolkit';

// 1. Create a Slice
const counterSlice = createSlice({
  name: 'counter',
  initialState: { count: 0 },
  reducers: {
    increment: (state) => {
      state.count += 1;
    },
    decrement: (state) => {
      state.count -= 1;
    },
  },
});

const { actions, reducer } = counterSlice;

// 2. Create Store
const store = configureStore({
  reducer: { counter: reducer },
});

// 3. Dispatch Actions
store.dispatch(actions.increment());
console.log(store.getState()); // { counter: { count: 1 } }
```

> **Advantages of Redux Toolkit**:

* **Less boilerplate**: `createSlice` handles both action creators and reducers.
* **Easier setup**: `configureStore` simplifies store setup and includes Redux DevTools by default.

---

### 🔵 **Async Actions with Redux Thunk**

Handling **asynchronous actions** (e.g., fetching data from an API) can be done using **Redux Thunk** middleware. It allows you to return functions instead of actions, enabling you to dispatch multiple actions within a function.

#### Key Concepts:

* **Thunk**: A function that can dispatch actions asynchronously.
* **Dispatching async actions**: Thunks help handle async processes like network requests and dispatch actions based on the outcome.

#### Example with Redux Thunk:

```tsx
import { createSlice, configureStore } from '@reduxjs/toolkit';
import thunk from 'redux-thunk';

// 1. Create Slice with Async Thunks
const userSlice = createSlice({
  name: 'user',
  initialState: { user: null, loading: false },
  reducers: {
    setUser: (state, action) => {
      state.user = action.payload;
      state.loading = false;
    },
    setLoading: (state) => {
      state.loading = true;
    },
  },
});

const { actions, reducer } = userSlice;

// 2. Async Thunk (Fetch User)
const fetchUser = () => async (dispatch) => {
  dispatch(actions.setLoading());
  const response = await fetch('/api/user');
  const data = await response.json();
  dispatch(actions.setUser(data));
};

// 3. Create Store
const store = configureStore({
  reducer: { user: reducer },
  middleware: (getDefaultMiddleware) => getDefaultMiddleware().concat(thunk),
});

// 4. Dispatch Async Action
store.dispatch(fetchUser());
```

* **`fetchUser`** is an async action created using a thunk, which dispatches `setLoading` and `setUser` based on the API response.

---

### 🟡 **Summary**

1. **React Context API**:

   * Simple state management using `Provider` and `useContext`.
   * Great for smaller apps or global state.

2. **Redux Basics**:

   * Centralizes state in a store.
   * Uses **Actions** to send data and **Reducers** to update state.

3. **Redux Toolkit**:

   * Reduces boilerplate with `createSlice`, `configureStore`.
   * Ideal for simplifying Redux setup.

4. **Async Actions with Redux Thunk**:

   * Allows handling async operations (e.g., API calls).
   * Uses **Thunk** middleware to dispatch async actions.

---

Here’s how you can handle **Forms & Validation** in **React Native**, specifically focusing on **Controlled vs Uncontrolled Components**, **Formik**, **React Hook Form**, and **Validation using Yup**.

---

## 🟡 **7. Forms & Validation in React Native**

Handling forms and validation in React Native can be done using controlled and uncontrolled components, form libraries like **Formik** and **React Hook Form**, and validation libraries such as **Yup**.

---

### 🔲 **Controlled vs Uncontrolled Components in React Native**

#### **Controlled Components**

In controlled components, form data is managed by React state, meaning that React has complete control over the input values. You use the `useState` hook to manage form data, and any change in the form input triggers a state update.

##### Example in React Native:

```tsx
import React, { useState } from 'react';
import { View, TextInput, Button, Text } from 'react-native';

const ControlledForm = () => {
  const [name, setName] = useState('');

  const handleChange = (text: string) => setName(text);

  const handleSubmit = () => {
    console.log('Form submitted with name:', name);
  };

  return (
    <View>
      <TextInput
        placeholder="Enter your name"
        value={name}
        onChangeText={handleChange}
        style={{ height: 40, borderColor: 'gray', borderWidth: 1, marginBottom: 10 }}
      />
      <Button title="Submit" onPress={handleSubmit} />
    </View>
  );
};

export default ControlledForm;
```

* **Controlled Input**: The `TextInput` value is managed using the `useState` hook.
* **onChangeText**: Updates the state with the current input value.

---

#### **Uncontrolled Components**

Uncontrolled components manage form data using the **refs** API, meaning React doesn't directly manage the input values, and instead, it relies on the underlying DOM.

##### Example in React Native:

```tsx
import React, { useRef } from 'react';
import { View, TextInput, Button } from 'react-native';

const UncontrolledForm = () => {
  const nameInput = useRef<TextInput>(null);

  const handleSubmit = () => {
    const name = nameInput.current?.value; // Access the value via ref
    console.log('Form submitted with name:', name);
  };

  return (
    <View>
      <TextInput
        ref={nameInput}
        placeholder="Enter your name"
        style={{ height: 40, borderColor: 'gray', borderWidth: 1, marginBottom: 10 }}
      />
      <Button title="Submit" onPress={handleSubmit} />
    </View>
  );
};

export default UncontrolledForm;
```

* **Uncontrolled Input**: The `TextInput` value is accessed via the `ref`, not through React state.

---

### 🔴 **Form Libraries in React Native: Formik vs React Hook Form**

**Formik** and **React Hook Form** are both popular libraries to simplify form handling in React Native, including managing form state, validation, and error handling.

---

#### **Formik in React Native**

Formik is a powerful form library that makes handling form state and validation much easier. It works well with **Yup** for validation and simplifies form management by abstracting the handling of form state, errors, and submission.

##### Example using Formik in React Native:

```tsx
import React from 'react';
import { View, TextInput, Button, Text } from 'react-native';
import { Formik } from 'formik';
import * as Yup from 'yup';

const validationSchema = Yup.object({
  name: Yup.string().required('Name is required').min(2, 'Name must be at least 2 characters'),
});

const FormikExample = () => (
  <Formik
    initialValues={{ name: '' }}
    validationSchema={validationSchema}
    onSubmit={(values) => {
      console.log('Form submitted with values:', values);
    }}
  >
    {({ handleChange, handleBlur, handleSubmit, values, errors, touched }) => (
      <View>
        <TextInput
          placeholder="Enter your name"
          onChangeText={handleChange('name')}
          onBlur={handleBlur('name')}
          value={values.name}
          style={{ height: 40, borderColor: 'gray', borderWidth: 1, marginBottom: 10 }}
        />
        {touched.name && errors.name && <Text style={{ color: 'red' }}>{errors.name}</Text>}
        <Button title="Submit" onPress={handleSubmit} />
      </View>
    )}
  </Formik>
);

export default FormikExample;
```

* **Formik** manages form state, validation, and error handling.
* **Yup** is used for schema-based validation.
* **`handleChange`** and **`handleBlur`** handle input changes and blur events.
* **`errors`** and **`touched`** provide validation feedback.

---

#### **React Hook Form in React Native**

React Hook Form is a lightweight and performant library for handling forms in React Native. It minimizes re-renders by leveraging React hooks and provides a simple API for form validation and submission.

##### Example using React Hook Form in React Native:

```tsx
import React from 'react';
import { View, TextInput, Button, Text } from 'react-native';
import { useForm, Controller } from 'react-hook-form';
import * as Yup from 'yup';
import { yupResolver } from '@hookform/resolvers/yup';

const validationSchema = Yup.object({
  name: Yup.string().required('Name is required').min(2, 'Name must be at least 2 characters'),
});

const ReactHookFormExample = () => {
  const { control, handleSubmit, formState: { errors } } = useForm({
    resolver: yupResolver(validationSchema),
  });

  const onSubmit = (data: any) => {
    console.log('Form submitted with data:', data);
  };

  return (
    <View>
      <Controller
        control={control}
        render={({ field: { onChange, onBlur, value } }) => (
          <TextInput
            placeholder="Enter your name"
            onBlur={onBlur}
            onChangeText={onChange}
            value={value}
            style={{ height: 40, borderColor: 'gray', borderWidth: 1, marginBottom: 10 }}
          />
        )}
        name="name"
      />
      {errors.name && <Text style={{ color: 'red' }}>{errors.name.message}</Text>}
      <Button title="Submit" onPress={handleSubmit(onSubmit)} />
    </View>
  );
};

export default ReactHookFormExample;
```

* **React Hook Form** simplifies form state management using `Controller` to wrap each input field.
* **`yupResolver`** integrates **Yup** validation with React Hook Form.
* **`handleSubmit`** is used to trigger form submission.

---

### 🟢 **Validation using Yup**

**Yup** is a validation library that works well with both **Formik** and **React Hook Form**. It is schema-based and provides built-in methods for validating strings, numbers, dates, arrays, and more.

#### Key Features:

* **Schema-based validation**.
* **Chainable methods** to define validation rules.
* **Custom validation** logic.

#### Example using Yup with Formik:

```tsx
import * as Yup from 'yup';

const validationSchema = Yup.object({
  name: Yup.string().required('Name is required').min(2, 'Name must be at least 2 characters'),
  email: Yup.string().email('Invalid email format').required('Email is required'),
});

// Use this schema with Formik or React Hook Form
```

* **Yup.string()**: Validates a string.
* **Yup.number()**: Validates a number.
* **Yup.email()**: Ensures the field is a valid email.

#### Common Validation Methods:

* **required**: Ensures the field is not empty.
* **min/max**: Enforces minimum/maximum length.
* **email**: Validates email format.
* **matches**: Validates input using regex.

---

### 🟡 **Summary**

1. **Controlled vs Uncontrolled Components in React Native**:

   * **Controlled**: Data is managed via React state (`useState`).
   * **Uncontrolled**: Data is accessed via refs, not React state.

2. **Formik**:

   * Provides easy-to-use form state management and validation with **Yup**.
   * Great for complex forms with built-in error handling.

3. **React Hook Form**:

   * Minimal re-renders and uses hooks for form management.
   * Provides a performant and simple API for handling forms and validation.

4. **Yup**:

   * Schema-based validation that works seamlessly with **Formik** and **React Hook Form**.

---

Here’s a detailed breakdown of **Networking** in **React Native**:

---

## 🟡 **8. Networking in React Native**

Networking is a crucial part of mobile development, as it allows apps to communicate with remote servers to fetch or send data. In React Native, you can use native JavaScript solutions like **Fetch API** or third-party libraries like **Axios** to make HTTP requests. Additionally, handling errors and showing loading states during network requests is essential for a smooth user experience.

---

### 🔲 **Fetch API**

The **Fetch API** is a native JavaScript API used to make HTTP requests. It is promise-based and supports both `GET` and `POST` requests, as well as other HTTP methods like `PUT`, `DELETE`, etc.

#### Example of GET request using **Fetch**:

```tsx
import React, { useState, useEffect } from 'react';
import { View, Text, Button, ActivityIndicator } from 'react-native';

const FetchExample = () => {
  const [data, setData] = useState<any>(null);
  const [loading, setLoading] = useState<boolean>(false);
  const [error, setError] = useState<string>('');

  const fetchData = async () => {
    setLoading(true);
    try {
      const response = await fetch('https://jsonplaceholder.typicode.com/posts');
      if (!response.ok) {
        throw new Error('Network response was not ok');
      }
      const data = await response.json();
      setData(data);
    } catch (error: any) {
      setError(error.message);
    } finally {
      setLoading(false);
    }
  };

  useEffect(() => {
    fetchData();
  }, []);

  if (loading) return <ActivityIndicator size="large" color="#0000ff" />;
  if (error) return <Text>Error: {error}</Text>;

  return (
    <View>
      <Text>Fetched Data:</Text>
      {data?.map((item: any) => (
        <Text key={item.id}>{item.title}</Text>
      ))}
      <Button title="Fetch Again" onPress={fetchData} />
    </View>
  );
};

export default FetchExample;
```

* **`fetch()`**: Sends a network request.
* **`response.json()`**: Converts the response body into JSON format.
* **Error Handling**: Catches errors in case of network issues or invalid responses.

---

### 🔴 **Axios for HTTP Requests**

**Axios** is a promise-based HTTP client for JavaScript that works in both the browser and Node.js environments. It provides a simpler and more feature-rich API than `fetch()`, such as automatic JSON transformation and easier handling of request and response interceptors.

#### Example of GET request using **Axios**:

1. First, install Axios:

```bash
npm install axios
```

2. Then, use it in your app:

```tsx
import React, { useState, useEffect } from 'react';
import { View, Text, Button, ActivityIndicator } from 'react-native';
import axios from 'axios';

const AxiosExample = () => {
  const [data, setData] = useState<any>(null);
  const [loading, setLoading] = useState<boolean>(false);
  const [error, setError] = useState<string>('');

  const fetchData = async () => {
    setLoading(true);
    try {
      const response = await axios.get('https://jsonplaceholder.typicode.com/posts');
      setData(response.data);
    } catch (error: any) {
      setError(error.message);
    } finally {
      setLoading(false);
    }
  };

  useEffect(() => {
    fetchData();
  }, []);

  if (loading) return <ActivityIndicator size="large" color="#0000ff" />;
  if (error) return <Text>Error: {error}</Text>;

  return (
    <View>
      <Text>Fetched Data:</Text>
      {data?.map((item: any) => (
        <Text key={item.id}>{item.title}</Text>
      ))}
      <Button title="Fetch Again" onPress={fetchData} />
    </View>
  );
};

export default AxiosExample;
```

* **`axios.get()`**: Sends a `GET` request.
* **Error Handling**: Catches errors related to network failures or invalid responses.

**Advantages of Axios over Fetch**:

* Automatically transforms response data to JSON.
* Built-in request cancellation support.
* Can easily set headers, timeout, and intercept requests/responses.

---

### 🟢 **Working with REST APIs**

React Native apps often interact with REST APIs. A RESTful API allows you to send requests (like `GET`, `POST`, `PUT`, `DELETE`) to manipulate resources on the server. To interact with a REST API, you'll send HTTP requests (like `GET` to retrieve data, `POST` to create new records) and handle responses (status codes, data, etc.).

#### Example of POST request using **Fetch**:

```tsx
const postData = async () => {
  const dataToSend = { title: 'New Post', body: 'This is a new post', userId: 1 };

  const response = await fetch('https://jsonplaceholder.typicode.com/posts', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json',
    },
    body: JSON.stringify(dataToSend),
  });

  const data = await response.json();
  console.log('Post response data:', data);
};
```

* **`POST`**: Used to send new data to the server.
* **`headers`**: Specifies content type (JSON in this case).
* **`body`**: The data being sent to the server, typically in JSON format.

#### Example of PUT request using **Axios**:

```tsx
const updateData = async () => {
  const dataToUpdate = { id: 1, title: 'Updated Post' };

  try {
    const response = await axios.put('https://jsonplaceholder.typicode.com/posts/1', dataToUpdate);
    console.log('Update response data:', response.data);
  } catch (error) {
    console.error('Error updating data:', error);
  }
};
```

* **`PUT`**: Used to update existing data.

---

### 🔶 **Error Handling and Loaders**

Handling errors and showing loaders are crucial for a smooth user experience when fetching data from a remote server. React Native provides simple ways to manage loading states and display errors.

#### **Error Handling**:

Error handling ensures that the app doesn’t crash and provides useful feedback to users in case of network issues or server-side errors.

##### Example of Error Handling:

```tsx
try {
  const response = await fetch('https://example.com/data');
  if (!response.ok) {
    throw new Error('Failed to fetch data');
  }
  const data = await response.json();
  setData(data);
} catch (error: any) {
  setError(error.message);
}
```

* If the response status code is not `ok`, an error is thrown.
* Errors are caught in the `catch` block, where we can handle them accordingly.

#### **Loaders (Activity Indicator)**:

While waiting for data to load, you can show a loading spinner or indicator. React Native provides the **`ActivityIndicator`** component for this.

##### Example of Loaders:

```tsx
import { ActivityIndicator } from 'react-native';

if (loading) {
  return <ActivityIndicator size="large" color="#0000ff" />;
}
```

* **`ActivityIndicator`**: A simple spinning loader to indicate that data is loading.

---

### 🟡 **Summary**

1. **Fetch API**:

   * Native JavaScript API for making HTTP requests.
   * Provides basic functionality for `GET`, `POST`, `PUT`, `DELETE` requests.
   * Works well for simple use cases but lacks some advanced features.

2. **Axios**:

   * A promise-based HTTP client with a more feature-rich API compared to Fetch.
   * Automatically handles JSON transformation, and provides request interceptors and error handling.
   * Useful for more complex requests and advanced configurations.

3. **Working with REST APIs**:

   * REST APIs allow interaction with remote resources.
   * Common HTTP methods: `GET`, `POST`, `PUT`, `DELETE`.

4. **Error Handling and Loaders**:

   * **Error handling** ensures the app gracefully handles issues like network failures.
   * **ActivityIndicator** provides a way to show a loading spinner while data is being fetched.

---

Here’s an overview of **Persistent Storage** in **React Native** including how to use **AsyncStorage**, **MMKV**, **Realm**, and **SecureStore** for storing data in your app.

---

## 🟡 **9. Persistent Storage in React Native**

Persistent storage is essential for storing data locally on a user's device, enabling apps to retain data even when the app is closed or restarted. React Native provides several solutions for local storage, each serving different needs, from basic key-value pairs to secure, high-performance databases.

---

### 🔲 **AsyncStorage**

**AsyncStorage** is a simple, asynchronous, persistent key-value storage system. It’s part of the **React Native core** and is suitable for storing small to medium-sized data like user preferences, settings, or authentication tokens.

#### Example of Using AsyncStorage:

1. First, install **AsyncStorage** if you're using React Native 0.59 or lower:

   ```bash
   npm install @react-native-async-storage/async-storage
   ```

2. Use **AsyncStorage** to store and retrieve data:

```tsx
import React, { useState, useEffect } from 'react';
import { View, Button, Text } from 'react-native';
import AsyncStorage from '@react-native-async-storage/async-storage';

const AsyncStorageExample = () => {
  const [name, setName] = useState<string>('');

  const storeData = async () => {
    try {
      await AsyncStorage.setItem('@name', 'John Doe');
      console.log('Name stored');
    } catch (e) {
      console.error('Error storing data', e);
    }
  };

  const getData = async () => {
    try {
      const value = await AsyncStorage.getItem('@name');
      if (value !== null) {
        setName(value);
      }
    } catch (e) {
      console.error('Error retrieving data', e);
    }
  };

  useEffect(() => {
    getData();
  }, []);

  return (
    <View>
      <Text>Stored Name: {name}</Text>
      <Button title="Store Data" onPress={storeData} />
    </View>
  );
};

export default AsyncStorageExample;
```

* **`AsyncStorage.setItem()`**: Stores data.
* **`AsyncStorage.getItem()`**: Retrieves stored data.
* **`AsyncStorage.removeItem()`**: Removes data.

**Limitations**:

* **AsyncStorage** is not ideal for storing large datasets or highly structured data.
* The storage is not encrypted, so sensitive information should not be stored directly.

---

### 🔴 **MMKV or Realm (For Faster and Secure Storage)**

#### **MMKV (Memory-Mapped Key-Value)**

**MMKV** is a fast, secure, and efficient key-value storage system. It’s more performance-oriented than **AsyncStorage** and is particularly useful when storing larger amounts of data. MMKV provides encryption and is faster, using memory-mapped files to reduce disk I/O.

##### Example of Using MMKV:

1. First, install MMKV:

   ```bash
   npm install react-native-mmkv
   ```

2. Example usage:

```tsx
import React from 'react';
import { View, Button, Text } from 'react-native';
import { MMKV } from 'react-native-mmkv';

const storage = new MMKV();

const MMKVExample = () => {
  const storeData = () => {
    storage.set('user', 'John Doe');
    console.log('Data stored in MMKV');
  };

  const getData = () => {
    const value = storage.getString('user');
    console.log('Retrieved value from MMKV:', value);
  };

  return (
    <View>
      <Button title="Store Data in MMKV" onPress={storeData} />
      <Button title="Get Data from MMKV" onPress={getData} />
    </View>
  );
};

export default MMKVExample;
```

* **MMKV** provides a faster alternative to **AsyncStorage**.
* Data can be encrypted and accessed efficiently.

#### **Advantages of MMKV**:

* **Faster performance** compared to AsyncStorage.
* **Encryption** support for sensitive data.
* Suitable for larger datasets due to its memory-mapped architecture.

---

#### **Realm (For Complex Data Storage)**

**Realm** is a mobile-first database designed for high performance and offline-first apps. It is a **NoSQL database** and provides more structured data storage, making it an ideal choice for apps that need to persist complex data structures.

##### Example of Using Realm:

1. First, install Realm:

   ```bash
   npm install realm
   ```

2. Example usage:

```tsx
import React, { useEffect, useState } from 'react';
import { View, Text, Button } from 'react-native';
import Realm from 'realm';

// Define schema for the Realm database
const CarSchema = {
  name: 'Car',
  properties: {
    make: 'string',
    model: 'string',
    year: 'int',
  },
};

const RealmExample = () => {
  const [cars, setCars] = useState<any[]>([]);

  useEffect(() => {
    const realm = new Realm({ schema: [CarSchema] });
    const storedCars = realm.objects('Car');
    setCars(storedCars);
  }, []);

  const addCar = () => {
    const realm = new Realm({ schema: [CarSchema] });
    realm.write(() => {
      realm.create('Car', {
        make: 'Tesla',
        model: 'Model S',
        year: 2021,
      });
    });
    console.log('Car added to Realm');
  };

  return (
    <View>
      <Button title="Add Car" onPress={addCar} />
      <Text>Cars in Realm:</Text>
      {cars.map((car, index) => (
        <Text key={index}>{`${car.make} ${car.model} (${car.year})`}</Text>
      ))}
    </View>
  );
};

export default RealmExample;
```

* **`Realm.create()`**: Adds new records to the database.
* **`realm.objects()`**: Retrieves records from the database.

**Advantages of Realm**:

* **Complex data models**: Ideal for structured data (objects, relationships, etc.).
* **Offline-first**: Supports offline data storage and synchronization.
* **Built-in encryption**: Provides security for sensitive data.
* **Cross-platform**: Works seamlessly on both iOS and Android.

---

### 🟢 **SecureStore (For Storing Sensitive Data)**

**SecureStore** is a solution provided by **Expo** for storing sensitive information, such as authentication tokens or passwords, securely on a device. It uses platform-specific secure storage solutions like **Keychain** on iOS and **Keystore** on Android.

#### Example of Using SecureStore:

1. First, install SecureStore (if using Expo):

   ```bash
   expo install expo-secure-store
   ```

2. Example usage:

```tsx
import React, { useState } from 'react';
import { View, Button, Text } from 'react-native';
import * as SecureStore from 'expo-secure-store';

const SecureStoreExample = () => {
  const [value, setValue] = useState<string>('');

  const storeSecureData = async () => {
    try {
      await SecureStore.setItemAsync('user_token', 'secure_token_123');
      console.log('Token stored securely');
    } catch (error) {
      console.error('Error storing secure data', error);
    }
  };

  const getSecureData = async () => {
    try {
      const storedValue = await SecureStore.getItemAsync('user_token');
      if (storedValue) {
        setValue(storedValue);
      }
    } catch (error) {
      console.error('Error retrieving secure data', error);
    }
  };

  return (
    <View>
      <Button title="Store Secure Data" onPress={storeSecureData} />
      <Button title="Get Secure Data" onPress={getSecureData} />
      <Text>Stored Token: {value}</Text>
    </View>
  );
};

export default SecureStoreExample;
```

* **`SecureStore.setItemAsync()`**: Stores sensitive data securely.
* **`SecureStore.getItemAsync()`**: Retrieves securely stored data.

**Advantages of SecureStore**:

* **Highly secure** storage solution.
* Uses platform-specific secure mechanisms (**Keychain** for iOS, **Keystore** for Android).
* Ideal for storing sensitive information like tokens, passwords, or encryption keys.

---

### 🟡 **Summary**

1. **AsyncStorage**:

   * Simple, asynchronous, key-value storage for small amounts of data.
   * Suitable for user preferences, settings, or simple app states.

2. **MMKV**:

   * Fast, memory-mapped key-value storage.
   * Ideal for large datasets and high-performance apps.
   * Supports encryption.

3. **Realm**:

   * A full-fledged NoSQL database, great for complex data models.
   * Supports offline-first apps and automatic synchronization.
   * Built-in encryption for data security.

4. **SecureStore**:

   * Secure storage solution for sensitive data like tokens or passwords.
   * Uses platform-native mechanisms (Keychain/Keystore).
   * Available through Expo.

### 🟡 **10. Device Features & APIs in React Native**

React Native provides access to many of the device's hardware features and APIs, which are essential for building feature-rich mobile applications. You can leverage libraries like **Expo** and **React Native** modules to interact with the camera, location services, handle permissions, notifications, and deep linking.

---

### 🔲 **1. Camera (expo-camera or react-native-camera)**

Accessing the camera is a common use case in many mobile apps, like capturing photos or scanning QR codes. There are two main libraries to achieve this in React Native: **expo-camera** (for Expo managed workflow) and **react-native-camera** (for non-Expo React Native apps).

#### Example with Expo Camera:

1. First, install Expo Camera:

   ```bash
   expo install expo-camera
   ```

2. Usage example:

```tsx
import React, { useState, useEffect } from 'react';
import { View, Text, Button } from 'react-native';
import { Camera } from 'expo-camera';

const CameraExample = () => {
  const [hasPermission, setHasPermission] = useState<boolean | null>(null);
  const [type, setType] = useState(Camera.Constants.Type.back);
  const [camera, setCamera] = useState<Camera | null>(null);

  useEffect(() => {
    const getPermission = async () => {
      const { status } = await Camera.requestPermissionsAsync();
      setHasPermission(status === 'granted');
    };
    getPermission();
  }, []);

  if (hasPermission === null) {
    return <Text>Requesting camera permission...</Text>;
  }
  if (hasPermission === false) {
    return <Text>No access to camera</Text>;
  }

  const takePicture = async () => {
    if (camera) {
      const photo = await camera.takePictureAsync();
      console.log('Photo taken:', photo);
    }
  };

  return (
    <View style={{ flex: 1 }}>
      <Camera style={{ flex: 1 }} type={type} ref={(ref) => setCamera(ref)}>
        <Button title="Take Picture" onPress={takePicture} />
      </Camera>
    </View>
  );
};

export default CameraExample;
```

* **`Camera.requestPermissionsAsync()`**: Requests permission to access the camera.
* **`camera.takePictureAsync()`**: Takes a picture using the camera.

---

### 🔴 **2. Location**

To access the device’s geolocation (latitude and longitude), React Native offers a variety of libraries. **Expo-location** is useful in Expo projects, while **react-native-geolocation-service** is recommended for non-Expo apps.

#### Example with Expo Location:

1. Install Expo Location:

   ```bash
   expo install expo-location
   ```

2. Usage example:

```tsx
import React, { useState, useEffect } from 'react';
import { View, Text, Button } from 'react-native';
import * as Location from 'expo-location';

const LocationExample = () => {
  const [location, setLocation] = useState<any>(null);
  const [errorMsg, setErrorMsg] = useState<string>('');

  useEffect(() => {
    const getLocation = async () => {
      let { status } = await Location.requestForegroundPermissionsAsync();
      if (status !== 'granted') {
        setErrorMsg('Permission to access location was denied');
        return;
      }

      let locationData = await Location.getCurrentPositionAsync({});
      setLocation(locationData);
    };

    getLocation();
  }, []);

  return (
    <View>
      {errorMsg ? (
        <Text>{errorMsg}</Text>
      ) : location ? (
        <Text>
          Latitude: {location.coords.latitude}, Longitude: {location.coords.longitude}
        </Text>
      ) : (
        <Text>Getting location...</Text>
      )}
    </View>
  );
};

export default LocationExample;
```

* **`Location.requestForegroundPermissionsAsync()`**: Requests location access permission.
* **`Location.getCurrentPositionAsync()`**: Fetches the current geolocation.

---

### 🟡 **3. Permissions**

Handling permissions is an essential part of app development. **Expo Permissions** is available for Expo-based projects, while for non-Expo projects, you can use **react-native-permissions** to manage permissions.

#### Example with Expo Permissions (Camera Permission):

```tsx
import React, { useEffect, useState } from 'react';
import { Text, View } from 'react-native';
import * as Permissions from 'expo-permissions';

const PermissionsExample = () => {
  const [status, setStatus] = useState<string>('');

  useEffect(() => {
    const getPermission = async () => {
      const { status } = await Permissions.askAsync(Permissions.CAMERA);
      setStatus(status);
    };
    getPermission();
  }, []);

  return (
    <View>
      <Text>Camera Permission Status: {status}</Text>
    </View>
  );
};

export default PermissionsExample;
```

* **`Permissions.askAsync()`**: Requests permission for the specified feature (camera, location, etc.).

---

### 🔲 **4. Push Notifications (Expo Notifications or Firebase)**

Push notifications allow you to send alerts or updates to your app users. You can either use **Expo Notifications** or integrate **Firebase Cloud Messaging (FCM)** for React Native projects.

#### Example with Expo Notifications:

1. Install the required libraries:

   ```bash
   expo install expo-notifications
   ```

2. Example usage:

```tsx
import React, { useEffect } from 'react';
import { Button, Platform, Text, View } from 'react-native';
import * as Notifications from 'expo-notifications';

const PushNotificationExample = () => {
  useEffect(() => {
    const subscription = Notifications.addNotificationReceivedListener((notification) => {
      console.log('Notification received:', notification);
    });

    return () => subscription.remove();
  }, []);

  const sendPushNotification = async () => {
    const message = {
      to: '<Expo Push Token>',
      sound: 'default',
      title: 'Test Notification',
      body: 'This is a test notification!',
    };
    await Notifications.scheduleNotificationAsync({
      content: message,
      trigger: null,
    });
  };

  return (
    <View>
      <Button title="Send Notification" onPress={sendPushNotification} />
    </View>
  );
};

export default PushNotificationExample;
```

* **`Notifications.addNotificationReceivedListener()`**: Handles notifications when received.
* **`Notifications.scheduleNotificationAsync()`**: Schedules a local notification.

#### Firebase Push Notifications:

If you're using **Firebase Cloud Messaging (FCM)**, Firebase SDK integration would be required for both **iOS** and **Android**. Firebase setup includes handling push tokens, sending notifications through Firebase Cloud, and receiving them in your React Native app.

---

### 🟢 **5. Deep Linking**

**Deep linking** enables your app to respond to specific URLs and navigate to a particular screen directly. It’s useful for allowing your app to open directly from external links or when shared between apps.

#### Example of Deep Linking in React Native:

1. First, configure your app to handle deep links:

   * **iOS**: Configure `Info.plist` to support deep links.
   * **Android**: Configure `AndroidManifest.xml` to define URL schemes.

2. Handle deep linking in your app:

```tsx
import React, { useEffect } from 'react';
import { View, Text } from 'react-native';
import { Linking } from 'react-native';

const DeepLinkingExample = () => {
  useEffect(() => {
    const handleDeepLink = (event: any) => {
      const data = event.url;
      console.log('Deep Link URL:', data);
    };

    Linking.addEventListener('url', handleDeepLink);

    return () => {
      Linking.removeEventListener('url', handleDeepLink);
    };
  }, []);

  return (
    <View>
      <Text>Waiting for deep link...</Text>
    </View>
  );
};

export default DeepLinkingExample;
```

* **`Linking.addEventListener('url')`**: Listens for deep links and processes the URL.
* **`Linking.openURL()`**: Opens a URL within your app.

**Setting Up Deep Links**:

* **iOS**: Update `Info.plist` to declare URL schemes.
* **Android**: Modify `AndroidManifest.xml` to declare your URL scheme.

---

### 🟡 **Summary**

* **Camera**: Access the device camera with libraries like **expo-camera** or **react-native-camera**.
* **Location**: Get geolocation using **expo-location** or **react-native-geolocation-service**.
* **Permissions**: Manage permissions with **expo-permissions** or **react-native-permissions**.
* **Push Notifications**: Send notifications using **Expo Notifications** or **Firebase Cloud Messaging**.
* **Deep Linking**: Handle URLs and open specific screens using **Linking** in React Native.

### 🟡 **11. Custom Components & Reusability in React Native**

Reusability and modularization are essential in React Native, especially for building scalable and maintainable applications. By creating custom components, you can significantly reduce the repetition of code and improve your app’s maintainability.

---

### 🔲 **1. Creating Reusable UI Components**

A **reusable UI component** is a component that can be used in multiple parts of your app without having to rewrite the same code. By abstracting logic and UI elements into separate components, you can reuse them as needed across the app.

#### Example of a Reusable Button Component:

```tsx
// components/Button.tsx
import React from 'react';
import { TouchableOpacity, Text, StyleSheet, GestureResponderEvent } from 'react-native';

interface ButtonProps {
  title: string;
  onPress: (event: GestureResponderEvent) => void;
  style?: object;
}

const Button: React.FC<ButtonProps> = ({ title, onPress, style }) => {
  return (
    <TouchableOpacity style={[styles.button, style]} onPress={onPress}>
      <Text style={styles.text}>{title}</Text>
    </TouchableOpacity>
  );
};

const styles = StyleSheet.create({
  button: {
    backgroundColor: '#007bff',
    padding: 10,
    borderRadius: 5,
  },
  text: {
    color: 'white',
    textAlign: 'center',
  },
});

export default Button;
```

#### Usage of the reusable Button component:

```tsx
import React from 'react';
import { View, Text } from 'react-native';
import Button from './components/Button';

const App = () => {
  const handlePress = () => {
    alert('Button Pressed!');
  };

  return (
    <View>
      <Text>Welcome to React Native!</Text>
      <Button title="Click Me" onPress={handlePress} />
    </View>
  );
};

export default App;
```

* **Props**: Custom components can accept **props** to allow flexibility and reusability. In the example above, the `Button` component receives a `title`, `onPress` function, and an optional `style` for customization.

---

### 🔴 **2. Component Composition**

**Component composition** is the practice of combining simple, reusable components to create more complex UI elements. This promotes flexibility and allows you to build UIs that are easy to maintain.

#### Example of Component Composition:

```tsx
// components/Card.tsx
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

const Card: React.FC = ({ children }) => {
  return (
    <View style={styles.card}>
      {children}
    </View>
  );
};

const styles = StyleSheet.create({
  card: {
    borderRadius: 10,
    padding: 15,
    backgroundColor: '#fff',
    shadowColor: '#000',
    shadowOpacity: 0.1,
    shadowRadius: 5,
    margin: 10,
  },
});

export default Card;
```

#### Usage of Card component with composition:

```tsx
import React from 'react';
import { View, Text } from 'react-native';
import Card from './components/Card';

const App = () => {
  return (
    <View>
      <Card>
        <Text>Card Title</Text>
        <Text>Card Description</Text>
      </Card>
      <Card>
        <Text>Another Card</Text>
      </Card>
    </View>
  );
};

export default App;
```

* **Composition**: The `Card` component is flexible enough to accept any children, allowing it to be used for different purposes with different content inside it.

---

### 🟡 **3. Conditional Rendering**

**Conditional rendering** in React Native allows you to display different UI components based on some conditions. You can use this technique to show/hide content, toggle between views, or render content dynamically based on the app state.

#### Example of Conditional Rendering:

```tsx
import React, { useState } from 'react';
import { View, Text, Button } from 'react-native';

const ConditionalRenderingExample = () => {
  const [isLoggedIn, setIsLoggedIn] = useState(false);

  const toggleLoginState = () => {
    setIsLoggedIn(!isLoggedIn);
  };

  return (
    <View>
      {isLoggedIn ? (
        <Text>Welcome, User!</Text>
      ) : (
        <Text>Please log in.</Text>
      )}
      <Button title={isLoggedIn ? 'Log Out' : 'Log In'} onPress={toggleLoginState} />
    </View>
  );
};

export default ConditionalRenderingExample;
```

* **Ternary Operator**: Conditional rendering often uses a ternary operator (`condition ? true : false`) to determine which component to render.

---

### 🔲 **4. FlatList and SectionList**

Both **FlatList** and **SectionList** are optimized components for rendering large lists of data in React Native. These components improve performance by rendering only the items that are visible on the screen, rather than rendering the entire list at once.

#### FlatList Example:

```tsx
import React from 'react';
import { FlatList, Text, View } from 'react-native';

const data = [
  { id: '1', name: 'John' },
  { id: '2', name: 'Jane' },
  { id: '3', name: 'Jack' },
];

const FlatListExample = () => {
  return (
    <FlatList
      data={data}
      renderItem={({ item }) => <Text>{item.name}</Text>}
      keyExtractor={(item) => item.id}
    />
  );
};

export default FlatListExample;
```

* **`renderItem`**: A function that takes each item from the `data` array and renders a component for each one.
* **`keyExtractor`**: A function to extract a unique key for each item in the list.

#### SectionList Example:

```tsx
import React from 'react';
import { SectionList, Text, View } from 'react-native';

const sections = [
  { title: 'A', data: ['Alice', 'Aaron'] },
  { title: 'B', data: ['Bob', 'Bill'] },
];

const SectionListExample = () => {
  return (
    <SectionList
      sections={sections}
      renderItem={({ item }) => <Text>{item}</Text>}
      renderSectionHeader={({ section }) => <Text style={{ fontWeight: 'bold' }}>{section.title}</Text>}
      keyExtractor={(item, index) => index.toString()}
    />
  );
};

export default SectionListExample;
```

* **`sections`**: Data is grouped into sections, and each section can have its own header and data.
* **`renderSectionHeader`**: Renders the section header (e.g., alphabetically grouped data).

---

### 🟢 **Summary**

* **Reusable UI Components**: Modularize your UI by creating components that accept props and can be reused across multiple places in your app.
* **Component Composition**: Combine simple components to create complex UIs while keeping the code modular and flexible.
* **Conditional Rendering**: Render UI elements based on app state or conditions using operators like the ternary operator.
* **FlatList & SectionList**: Use these components to handle and optimize large data lists efficiently in your app.

### 🟡 **12. Performance Optimization in React Native**

Performance is crucial in mobile apps as it directly impacts user experience. React Native offers several techniques to optimize performance, reduce memory usage, and ensure smooth rendering of components. Let's go through some key performance optimization strategies.

---

### 🔲 **1. Memoization: `React.memo`, `useMemo`, `useCallback`**

Memoization is the process of caching the result of a function call or component rendering, so that it doesn't need to be recomputed when the inputs haven't changed. This can improve performance by reducing unnecessary calculations or re-renders.

#### **`React.memo`** - For Component Memoization:

`React.memo` is a higher-order component that prevents re-rendering of a component if its props have not changed. It is useful for functional components to avoid re-rendering unless necessary.

```tsx
import React from 'react';

const MyComponent = React.memo(({ name }: { name: string }) => {
  console.log('Rendered:', name);
  return <Text>{name}</Text>;
});

export default MyComponent;
```

* `React.memo` only rerenders the component when the props have changed.

#### **`useMemo`** - For Memoizing Expensive Calculations:

`useMemo` is a hook used to memoize the result of expensive calculations, ensuring they are only recalculated when necessary.

```tsx
import React, { useMemo } from 'react';
import { Text } from 'react-native';

const ExpensiveCalculationComponent = ({ num }: { num: number }) => {
  const computedValue = useMemo(() => {
    console.log('Expensive calculation');
    return num * 2;
  }, [num]); // Recomputes only when `num` changes

  return <Text>{computedValue}</Text>;
};

export default ExpensiveCalculationComponent;
```

* **`useMemo`** helps optimize performance for expensive computations that should not run on every render unless dependencies change.

#### **`useCallback`** - For Memoizing Functions:

`useCallback` is used to memoize functions so that they are not recreated on every render. This is particularly useful when passing functions as props to child components that rely on reference equality to prevent unnecessary re-renders.

```tsx
import React, { useState, useCallback } from 'react';
import { Button } from 'react-native';

const ParentComponent = () => {
  const [count, setCount] = useState(0);

  const incrementCount = useCallback(() => {
    setCount((prevCount) => prevCount + 1);
  }, []); // Memoizes the function, so it doesn’t change unless necessary

  return <ChildComponent onClick={incrementCount} />;
};

const ChildComponent = React.memo(({ onClick }: { onClick: () => void }) => {
  console.log('Child re-rendered');
  return <Button title="Increment" onPress={onClick} />;
});

export default ParentComponent;
```

* **`useCallback`** ensures that the `incrementCount` function is not recreated on every render of the parent, optimizing the performance of child components.

---

### 🔴 **2. Lazy Loading Components**

**Lazy loading** refers to the practice of loading components only when they are needed, rather than loading everything upfront. This can significantly reduce the initial load time of the app.

#### Example of Lazy Loading with `React.lazy` and `Suspense`:

```tsx
import React, { Suspense, lazy } from 'react';
import { Text, View } from 'react-native';

const LazyLoadedComponent = lazy(() => import('./LazyLoadedComponent'));

const App = () => {
  return (
    <View>
      <Text>Welcome to React Native!</Text>
      <Suspense fallback={<Text>Loading...</Text>}>
        <LazyLoadedComponent />
      </Suspense>
    </View>
  );
};

export default App;
```

* **`React.lazy`**: Dynamically imports the component, making it load only when it's required.
* **`Suspense`**: Displays a loading state (e.g., a spinner or message) until the lazy-loaded component is ready.

---

### 🟡 **3. FlatList Optimization**

**FlatList** is a high-performance component for rendering large lists of data. However, for large lists, performance issues can arise if it's not properly optimized. Here are a few tips to optimize **FlatList**:

* **`keyExtractor`**: Always provide a unique key for each item to help React efficiently track items.

  ```tsx
  <FlatList
    data={data}
    keyExtractor={(item) => item.id.toString()}
    renderItem={({ item }) => <Text>{item.name}</Text>}
  />
  ```

* **`initialNumToRender`**: Controls how many items to render initially. Setting this to a reasonable value helps with the initial render performance.

  ```tsx
  <FlatList
    data={data}
    initialNumToRender={10} // Renders first 10 items initially
    renderItem={({ item }) => <Text>{item.name}</Text>}
  />
  ```

* **`getItemLayout`**: Provides a way to optimize item layout calculations for flat lists, especially when you know the size of each item in advance.

  ```tsx
  <FlatList
    data={data}
    getItemLayout={(data, index) => ({
      length: 50, // Height of each item
      offset: 50 * index,
      index,
    })}
    renderItem={({ item }) => <Text>{item.name}</Text>}
  />
  ```

* **`windowSize`**: Increases the number of items that are pre-rendered before they come into view. This improves the user experience by reducing lag when scrolling.

  ```tsx
  <FlatList
    data={data}
    windowSize={5} // Pre-renders 5 times the number of items that are visible
    renderItem={({ item }) => <Text>{item.name}</Text>}
  />
  ```

---

### 🔲 **4. Removing Unnecessary Re-renders**

Unnecessary re-renders can negatively impact performance. To reduce them:

* **Use `React.memo`**: Wrap components that don't rely on state or props changes in `React.memo` to avoid unnecessary re-renders.

* **Optimize State Changes**: Avoid setting state unnecessarily. Only update the state when needed, and try to batch state updates together.

* **Avoid Inline Functions**: Functions defined inline during every render (e.g., in JSX) will be recreated every time the component re-renders. Use `useCallback` to avoid this.

---

### 🟢 **5. Avoiding Memory Leaks**

Memory leaks occur when resources (e.g., event listeners, network requests) are not properly cleaned up, causing unnecessary memory consumption.

#### Clean Up Resources with `useEffect`:

```tsx
import React, { useEffect } from 'react';
import { Text } from 'react-native';

const ComponentWithEffect = () => {
  useEffect(() => {
    const timer = setInterval(() => {
      console.log('Timer tick');
    }, 1000);

    return () => {
      // Cleanup function to clear timer
      clearInterval(timer);
    };
  }, []);

  return <Text>Timer Example</Text>;
};

export default ComponentWithEffect;
```

* Always use the **cleanup function** in `useEffect` to avoid memory leaks when you are working with timers, event listeners, or subscriptions.

---

### 🟡 **Summary of Performance Optimization Techniques**

1. **Memoization**: Use `React.memo`, `useMemo`, and `useCallback` to prevent unnecessary re-renders and optimize calculations.
2. **Lazy Loading**: Use `React.lazy` and `Suspense` to load components only when needed, improving the app's initial loading performance.
3. **FlatList Optimization**: Use properties like `keyExtractor`, `initialNumToRender`, and `getItemLayout` to optimize list rendering.
4. **Avoiding Unnecessary Re-renders**: Use `React.memo`, avoid inline functions, and optimize state management to reduce unnecessary re-renders.
5. **Avoiding Memory Leaks**: Clean up resources in `useEffect` by returning a cleanup function to prevent memory leaks.

By applying these strategies, you can ensure that your React Native app performs efficiently, even with large datasets or complex user interfaces.

### 🟡 **13. Advanced Navigation in React Native**

Advanced navigation techniques in React Native help you build complex and dynamic app flows. Whether it's implementing custom transitions, enabling deep linking, managing nested navigators, or handling authentication flows, mastering these navigation patterns ensures a smooth user experience. Let's dive into these advanced concepts.

---

### 🔲 **1. Custom Transitions**

Custom transitions allow you to customize the way one screen transitions to another. By default, React Navigation provides basic transitions, but you can create your own to give your app a unique feel.

#### Example of Custom Transition with `react-navigation`:

React Navigation provides a way to configure custom transition animations using the `screenOptions` prop.

```tsx
import { createStackNavigator } from '@react-navigation/stack';
import { createAppContainer } from '@react-navigation/native';
import { View, Text, Button } from 'react-native';

const Stack = createStackNavigator();

const HomeScreen = ({ navigation }) => {
  return (
    <View>
      <Text>Home Screen</Text>
      <Button title="Go to Details" onPress={() => navigation.navigate('Details')} />
    </View>
  );
};

const DetailsScreen = () => {
  return (
    <View>
      <Text>Details Screen</Text>
    </View>
  );
};

const App = () => {
  return (
    <Stack.Navigator
      initialRouteName="Home"
      screenOptions={{
        gestureEnabled: true,
        cardStyleInterpolator: ({ current, next, layouts }) => {
          return {
            cardStyle: {
              transform: [
                {
                  translateX: current.progress.interpolate({
                    inputRange: [0, 1],
                    outputRange: [layouts.screen.width, 0],
                  }),
                },
              ],
            },
          };
        },
      }}
    >
      <Stack.Screen name="Home" component={HomeScreen} />
      <Stack.Screen name="Details" component={DetailsScreen} />
    </Stack.Navigator>
  );
};

export default createAppContainer(App);
```

* **`cardStyleInterpolator`**: Customizes the screen transition animation. In this example, the screen slides in from the right.
* You can configure various types of animations, such as scaling, fading, or rotating, by adjusting the properties of `cardStyleInterpolator`.

---

### 🔴 **2. Deep Linking**

Deep linking allows you to open specific screens of your app using URLs. This is especially useful for handling external links or push notifications that should open specific app content.

#### Setting Up Deep Linking:

You need to configure your app to handle specific URLs and route them to appropriate screens.

1. **Configure Deep Linking in `react-navigation`**:

```tsx
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';
import { Linking, View, Text } from 'react-native';

const Stack = createStackNavigator();

const HomeScreen = () => {
  return <Text>Home Screen</Text>;
};

const ProfileScreen = () => {
  return <Text>Profile Screen</Text>;
};

const App = () => {
  const linking = {
    prefixes: ['myapp://'],
    config: {
      screens: {
        Home: '',
        Profile: 'profile/:id',
      },
    },
  };

  return (
    <NavigationContainer linking={linking}>
      <Stack.Navigator initialRouteName="Home">
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Profile" component={ProfileScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
};

export default App;
```

2. **Handling a Deep Link**:

Now, if the app is opened with the deep link `myapp://profile/123`, it will automatically navigate to the `Profile` screen and pass the `id` parameter (123) as part of the route.

* **Prefixes**: The base URL scheme for deep linking (e.g., `myapp://`).
* **Config**: Maps the URL pattern to specific screens in the navigation system.

3. **Testing Deep Linking**:

To test deep linking in your React Native app, you can use the following command in the terminal:

```bash
npx react-native run-android
adb shell am start -W -a android.intent.action.VIEW -d "myapp://profile/123"
```

This command opens the `Profile` screen and passes `123` as the `id` parameter.

---

### 🟡 **3. Nested Navigators**

Nested navigators allow you to create complex navigation flows by embedding one navigator inside another. This is useful for organizing your app's flow and improving its scalability.

#### Example of Nested Stack and Tab Navigators:

```tsx
import React from 'react';
import { createStackNavigator } from '@react-navigation/stack';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';
import { NavigationContainer } from '@react-navigation/native';
import { View, Text } from 'react-native';

const Stack = createStackNavigator();
const Tab = createBottomTabNavigator();

const HomeScreen = () => <View><Text>Home Screen</Text></View>;
const SettingsScreen = () => <View><Text>Settings Screen</Text></View>;

const App = () => {
  return (
    <NavigationContainer>
      <Tab.Navigator>
        <Tab.Screen name="Home" component={HomeScreen} />
        <Tab.Screen name="Settings" component={SettingsScreen} />
      </Tab.Navigator>
    </NavigationContainer>
  );
};

export default App;
```

In this example, we have two navigators: a **tab navigator** (`Tab.Navigator`) and a **stack navigator** (`Stack.Navigator`). You can nest a stack navigator inside a tab navigator to create more complex navigation patterns.

---

### 🔲 **4. Authentication Flow (Public vs Private Routes)**

Handling authentication flow is crucial to restrict access to certain screens based on whether a user is logged in or not.

#### Example of Authentication Flow:

You can create a simple authentication flow with public (login/signup) and private (dashboard, profile) routes using `react-navigation` and conditional rendering.

```tsx
import React, { useState, useEffect } from 'react';
import { View, Text, Button } from 'react-native';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';

const Stack = createStackNavigator();

const LoginScreen = ({ navigation }) => {
  const handleLogin = () => {
    // Simulate login success
    navigation.replace('Dashboard');
  };

  return (
    <View>
      <Text>Login Screen</Text>
      <Button title="Login" onPress={handleLogin} />
    </View>
  );
};

const DashboardScreen = () => {
  return (
    <View>
      <Text>Dashboard Screen</Text>
    </View>
  );
};

const App = () => {
  const [isAuthenticated, setIsAuthenticated] = useState(false);

  useEffect(() => {
    // Simulate checking authentication state
    setIsAuthenticated(false); // Change this to true to simulate logged-in state
  }, []);

  return (
    <NavigationContainer>
      <Stack.Navigator>
        {isAuthenticated ? (
          <Stack.Screen name="Dashboard" component={DashboardScreen} />
        ) : (
          <Stack.Screen name="Login" component={LoginScreen} />
        )}
      </Stack.Navigator>
    </NavigationContainer>
  );
};

export default App;
```

* **Public Routes**: The `LoginScreen` is shown if the user is not authenticated.
* **Private Routes**: If the user is authenticated, they are redirected to the `DashboardScreen`.

#### Dynamic Route Replacement:

* **`navigation.replace`**: This method replaces the current screen with a new one, so when a user logs in, it avoids showing the login screen again.

---

### 🟢 **Summary of Advanced Navigation Techniques**

1. **Custom Transitions**: Customize screen transition animations to provide a unique user experience. You can adjust the transition styles using `cardStyleInterpolator`.
2. **Deep Linking**: Enable deep linking to open specific screens via URLs. Configure deep links with a prefix and routing rules.
3. **Nested Navigators**: Organize your app’s navigation flow by nesting multiple navigators, such as stack and tab navigators.
4. **Authentication Flow**: Create protected routes for authenticated users and public routes for login/signup. Manage routes based on the authentication state.

### 🟡 **14. Animations in React Native**

Animations play a crucial role in enhancing the user experience by adding smooth, interactive transitions and visual effects to your app. React Native provides multiple options for animations, including built-in APIs like `Animated` and `LayoutAnimation`, as well as third-party libraries like `Reanimated 2` and `React Native Gesture Handler`. Let’s dive into the different animation techniques and tools you can use to create engaging animations.

---

### 🔲 **1. LayoutAnimation and Animated API**

#### **LayoutAnimation**

`LayoutAnimation` allows for automatic animations when the layout of a view changes. This can be helpful for creating smooth transitions between state changes, like when elements are added, removed, or rearranged in the UI.

Example: Animating a view's layout change when adding/removing an item.

```tsx
import React, { useState } from 'react';
import { View, Text, Button, LayoutAnimation, StyleSheet } from 'react-native';

const LayoutAnimationExample = () => {
  const [show, setShow] = useState(true);

  const toggleView = () => {
    LayoutAnimation.configureNext(LayoutAnimation.Presets.easeInEaseOut);
    setShow(!show);
  };

  return (
    <View style={styles.container}>
      <Button title="Toggle View" onPress={toggleView} />
      {show && (
        <View style={styles.box}>
          <Text>Animated View</Text>
        </View>
      )}
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  box: {
    width: 200,
    height: 100,
    backgroundColor: 'skyblue',
    justifyContent: 'center',
    alignItems: 'center',
    marginTop: 20,
  },
});

export default LayoutAnimationExample;
```

* **`LayoutAnimation.configureNext()`**: Configures the next layout change animation.
* **`LayoutAnimation.Presets.easeInEaseOut`**: A preset for the animation, which eases in and out.

#### **Animated API**

The `Animated` API allows you to create more complex animations. It supports animations like fades, scaling, sliding, and much more.

Example: Creating a simple fade-in animation with the `Animated` API.

```tsx
import React, { useEffect, useRef } from 'react';
import { View, Text, Animated, StyleSheet } from 'react-native';

const AnimatedExample = () => {
  const fadeAnim = useRef(new Animated.Value(0)).current;

  useEffect(() => {
    Animated.timing(fadeAnim, {
      toValue: 1,
      duration: 1000,
      useNativeDriver: true,
    }).start();
  }, [fadeAnim]);

  return (
    <View style={styles.container}>
      <Animated.View style={[styles.box, { opacity: fadeAnim }]}>
        <Text style={styles.text}>Fading In!</Text>
      </Animated.View>
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  box: {
    width: 200,
    height: 100,
    backgroundColor: 'lightgreen',
    justifyContent: 'center',
    alignItems: 'center',
  },
  text: {
    fontSize: 20,
    color: 'white',
  },
});

export default AnimatedExample;
```

* **`Animated.Value()`**: A value that can be animated over time.
* **`Animated.timing()`**: A type of animation used to animate a value to a certain target value over a given duration.
* **`useNativeDriver: true`**: Use native driver for better performance when animating properties that are off the main thread (e.g., `opacity` and `transform`).

---

### 🔴 **2. Reanimated 2**

Reanimated 2 is a powerful and flexible animation library that provides more control over animations and gestures. It uses the worklet concept to run animations directly on the UI thread, which results in smoother animations with better performance.

#### **Basic Example with Reanimated 2**

To get started with Reanimated 2, you need to install it and set it up:

```bash
npm install react-native-reanimated
```

Here’s a basic example of a simple scale animation using Reanimated 2:

```tsx
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';
import Animated, { Easing, useSharedValue, withTiming } from 'react-native-reanimated';

const ReanimatedExample = () => {
  const scale = useSharedValue(1);

  const handlePress = () => {
    scale.value = withTiming(1.5, { duration: 500, easing: Easing.ease });
  };

  return (
    <View style={styles.container}>
      <Animated.View
        style={[styles.box, { transform: [{ scale: scale.value }] }]}
      >
        <Text style={styles.text}>Tap to Scale</Text>
      </Animated.View>
      <Text onPress={handlePress} style={styles.buttonText}>Press Me</Text>
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  box: {
    width: 200,
    height: 100,
    backgroundColor: 'coral',
    justifyContent: 'center',
    alignItems: 'center',
    marginBottom: 20,
  },
  text: {
    fontSize: 20,
    color: 'white',
  },
  buttonText: {
    fontSize: 20,
    color: 'blue',
    textDecorationLine: 'underline',
  },
});

export default ReanimatedExample;
```

* **`useSharedValue()`**: Defines a value that can be animated.
* **`withTiming()`**: Creates a smooth transition to a target value over time.

---

### 🟡 **3. Gesture Handler Integration**

The React Native Gesture Handler library is often used in conjunction with Reanimated to manage gestures such as taps, swipes, and drags. The combination of Reanimated 2 and Gesture Handler makes building interactive UIs easy.

#### **Using Gesture Handler and Reanimated**

Here’s an example where we combine a drag gesture with Reanimated to create a draggable view:

```tsx
import React from 'react';
import { View, StyleSheet } from 'react-native';
import Animated, { withSpring } from 'react-native-reanimated';
import { GestureHandlerRootView, PanGestureHandler } from 'react-native-gesture-handler';

const DraggableBox = () => {
  const translationX = new Animated.Value(0);
  const translationY = new Animated.Value(0);

  const onGestureEvent = Animated.event(
    [{ nativeEvent: { translationX, translationY } }],
    { useNativeDriver: true }
  );

  return (
    <GestureHandlerRootView style={styles.container}>
      <PanGestureHandler onGestureEvent={onGestureEvent}>
        <Animated.View
          style={[
            styles.box,
            {
              transform: [
                { translateX },
                { translateY },
              ],
            },
          ]}
        />
      </PanGestureHandler>
    </GestureHandlerRootView>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  box: {
    width: 150,
    height: 150,
    backgroundColor: 'purple',
    borderRadius: 10,
  },
});

export default DraggableBox;
```

* **`PanGestureHandler`**: A gesture handler that captures pan (drag) gestures.
* **`Animated.event()`**: Maps gesture events to animated values.
* **`useNativeDriver: true`**: Ensures the gesture and animation run on the native thread for smooth performance.

---

### 🟢 **4. Building Complex UI Interactions**

You can combine multiple animations and gestures to build complex UI interactions. For example, combining drag-and-drop with animations like scaling, rotating, or changing opacity.

#### Example: Draggable Card with Scale on Drag

```tsx
import React from 'react';
import { View, StyleSheet } from 'react-native';
import Animated, { withSpring, interpolate, Extrapolate } from 'react-native-reanimated';
import { GestureHandlerRootView, PanGestureHandler } from 'react-native-gesture-handler';

const DraggableCard = () => {
  const translationX = new Animated.Value(0);
  const translationY = new Animated.Value(0);

  const onGestureEvent = Animated.event(
    [{ nativeEvent: { translationX, translationY } }],
    { useNativeDriver: true }
  );

  const scale = interpolate(translationY, {
    inputRange: [-100, 0, 100],
    outputRange: [1.2, 1, 0.8],
    extrapolate: Extrapolate.CLAMP,
  });

  return (
    <GestureHandlerRootView style={styles.container}>
      <PanGestureHandler onGestureEvent={onGestureEvent}>
        <Animated.View
          style={[
            styles.card,
            {
              transform: [
                { translateX },
                { translateY },
                { scale },
              ],
            },
          ]}
        />
      </PanGestureHandler>
    </GestureHandlerRootView>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  card: {
    width: 300,
    height: 200,
    backgroundColor: 'salmon',
    borderRadius: 10,
  },
});

export default DraggableCard;
```

* **`interpolate()`**: Used to create custom mappings for animated values, such as changing the scale based on vertical drag.

---

### 🔴 **Summary of Animation Techniques**

1. **LayoutAnimation**: Automatically animates changes in the layout, like adding or removing items.
2. **Animated API**: Used to animate properties like opacity, transform, and position. Supports more complex animations and custom timing.
3. **Reanimated 2**: Provides smoother, more performant animations by running animations on the native thread.
4. **Gesture Handler Integration**: Combine Reanimated 2 with Gesture Handler to create interactive UIs like drag-and-drop or swipe gestures.
5. **Complex UI Interactions**: Build sophisticated animations combining gestures, scaling, rotation, and other transformations to create dynamic user interfaces.

### 🟡 **15. Testing in React Native**

Testing is a crucial part of the development process as it ensures your app works as expected, remains stable over time, and allows you to catch potential bugs early. React Native supports various testing strategies, including unit testing, component testing, snapshot testing, and mocking API calls.

In this section, we will cover how to set up and use Jest for unit testing, React Native Testing Library (RNTL) for component testing, snapshot testing, and how to mock API calls to simulate real-world scenarios.

---

### 🔲 **1. Unit Testing with Jest**

**Jest** is the default testing framework for React Native. It provides a simple setup for running unit tests and comes with built-in assertions, spies, and mocks.

#### **Setting Up Jest for React Native**

React Native comes pre-configured with Jest when you initialize a new project using the `react-native` CLI. If you’re using Expo, Jest is also pre-configured when you create a new project.

To get started with Jest:

1. **Install Jest (if not installed already)**:

```bash
npm install --save-dev jest @testing-library/react-native
```

2. **Update the `package.json` to configure Jest**:

```json
"jest": {
  "preset": "react-native",
  "transformIgnorePatterns": [
    "node_modules/(?!(@react-native|react-navigation|react-native-gesture-handler|react-native-reanimated)/)"
  ]
}
```

#### **Writing Unit Tests**

Here's an example of a simple unit test for a function:

```tsx
// sum.ts
export const sum = (a: number, b: number): number => a + b;
```

```tsx
// sum.test.ts
import { sum } from './sum';

describe('sum function', () => {
  it('adds two numbers correctly', () => {
    expect(sum(1, 2)).toBe(3);
  });

  it('adds negative numbers correctly', () => {
    expect(sum(-1, -2)).toBe(-3);
  });
});
```

* **`it()`**: Defines a test case.
* **`expect()`**: Defines an assertion to check the result.

#### **Running Jest Tests**

Run the following command to execute tests:

```bash
npm test
```

---

### 🔴 **2. Component Testing with React Native Testing Library (RNTL)**

**React Native Testing Library (RNTL)** is a library for testing React Native components. It encourages good testing practices by focusing on testing the behavior of components rather than their implementation details.

#### **Installation**

If not installed, install the required dependencies:

```bash
npm install --save-dev @testing-library/react-native @testing-library/jest-native
```

#### **Testing a Simple Component**

Let’s write a simple component and test it with RNTL.

```tsx
// Greeting.tsx
import React from 'react';
import { Text, View } from 'react-native';

interface GreetingProps {
  name: string;
}

const Greeting: React.FC<GreetingProps> = ({ name }) => (
  <View>
    <Text>Hello, {name}!</Text>
  </View>
);

export default Greeting;
```

Now, we’ll write a test for this component using React Native Testing Library.

```tsx
// Greeting.test.tsx
import React from 'react';
import { render } from '@testing-library/react-native';
import Greeting from './Greeting';

describe('<Greeting />', () => {
  it('renders the greeting message correctly', () => {
    const { getByText } = render(<Greeting name="John" />);
    getByText('Hello, John!');
  });
});
```

* **`render()`**: Renders the component into a virtual DOM.
* **`getByText()`**: Queries the rendered output to find a text node.

---

### 🟡 **3. Snapshot Testing**

Snapshot testing is a way to ensure that the rendered output of a component matches its expected output. Jest can take a "snapshot" of your component’s rendered output and compare it to future snapshots to detect any unexpected changes.

#### **Creating a Snapshot Test**

Here’s an example of how to write a snapshot test for the `Greeting` component:

```tsx
// Greeting.snapshot.test.tsx
import React from 'react';
import { render } from '@testing-library/react-native';
import Greeting from './Greeting';

describe('<Greeting />', () => {
  it('matches the snapshot', () => {
    const { toJSON } = render(<Greeting name="John" />);
    expect(toJSON()).toMatchSnapshot();
  });
});
```

* **`toJSON()`**: Converts the rendered component to a JSON object.
* **`toMatchSnapshot()`**: Compares the current rendered output with the stored snapshot.

When you run the test, Jest will generate a snapshot file in the `__snapshots__` folder. If the component’s output changes, Jest will notify you, and you can decide whether the change is intentional.

#### **Running Snapshot Tests**

To run tests and generate/update snapshots, use the following command:

```bash
npm test -- -u
```

---

### 🔲 **4. Mocking API Calls**

Mocking API calls is essential for testing components that interact with APIs. This allows you to simulate different responses without making actual network requests, which could be slow or unreliable.

#### **Mocking with Jest**

You can mock API calls using Jest’s `jest.mock()` function.

Here’s an example of how to mock an API call in a component:

```tsx
// api.ts
export const fetchUserData = async (userId: string) => {
  const response = await fetch(`https://api.example.com/user/${userId}`);
  const data = await response.json();
  return data;
};
```

Now, we’ll mock the `fetchUserData` API call.

```tsx
// fetchUserData.test.ts
import { fetchUserData } from './api';

jest.mock('./api', () => ({
  fetchUserData: jest.fn(),
}));

describe('fetchUserData', () => {
  it('fetches user data correctly', async () => {
    const mockData = { id: '1', name: 'John Doe' };
    fetchUserData.mockResolvedValue(mockData);

    const data = await fetchUserData('1');
    expect(data).toEqual(mockData);
  });

  it('handles errors correctly', async () => {
    fetchUserData.mockRejectedValue(new Error('Network Error'));

    try {
      await fetchUserData('1');
    } catch (error) {
      expect(error.message).toBe('Network Error');
    }
  });
});
```

* **`jest.mock()`**: Mocks the module or function.
* **`mockResolvedValue()`**: Mocks a successful API response.
* **`mockRejectedValue()`**: Mocks a failed API response.

---

### 🔴 **5. Conclusion**

By using **Jest**, **React Native Testing Library**, and **snapshot testing**, you can ensure that your components work as expected and remain stable throughout the development process. Mocking API calls allows you to simulate real-world scenarios without relying on an actual backend. Testing helps catch bugs early, improves code quality, and builds confidence in your application’s stability.

**Testing best practices:**

* **Test Behavior, Not Implementation:** Focus on testing how components behave rather than how they are implemented.
* **Keep Tests Simple and Isolated:** Write small, isolated tests that are easy to understand and maintain.
* **Run Tests Frequently:** Run tests regularly to catch bugs early and ensure consistent behavior.

### 🟡 **16. TypeScript with React Native**

TypeScript is a superset of JavaScript that adds static typing to the language, making it more robust and reliable, especially for larger applications. In a React Native project, TypeScript can help catch errors at compile time, improve code quality, and provide better development experiences with auto-completion and type safety.

In this section, we will explore how to set up TypeScript with React Native, type props, state, and navigation, and ensure type safety when working with Redux and API responses.

---

### 🔲 **1. Setting up TypeScript with React Native**

To use TypeScript with React Native, follow these steps:

#### **Step 1: Create a React Native Project with TypeScript**

When initializing a new React Native project, you can set up TypeScript directly by adding the `--template` flag.

```bash
npx react-native init MyApp --template react-native-template-typescript
```

This will create a new React Native project with TypeScript pre-configured. If you’re adding TypeScript to an existing React Native project, follow the steps below.

#### **Step 2: Installing TypeScript**

Install TypeScript and its related dependencies:

```bash
npm install --save-dev typescript @types/react @types/react-native
```

#### **Step 3: Adding TypeScript Configuration**

Create a `tsconfig.json` file at the root of your project. Here's a simple TypeScript configuration that works well for React Native:

```json
{
  "compilerOptions": {
    "allowJs": true,
    "jsx": "react-native",
    "esModuleInterop": true,
    "skipLibCheck": true,
    "strict": true,
    "forceConsistentCasingInFileNames": true,
    "noEmit": true
  },
  "include": [
    "src/**/*",
    "node_modules/react-native/types/**/*.d.ts"
  ]
}
```

This will ensure that TypeScript is properly configured for React Native development.

#### **Step 4: Rename Files to `.tsx`**

Rename your React component files from `.js` to `.tsx`. For any file that doesn't contain JSX, you can use `.ts` (e.g., for utility functions or non-UI code).

---

### 🔴 **2. Typing Props, State, and Navigation**

TypeScript works well with React Native, especially when typing props and state in components. Here’s how you can type different aspects of a React Native component.

#### **Typing Props**

To define prop types for a component, you use TypeScript’s `interface` or `type` keyword. Here’s an example of typing props for a functional component.

```tsx
// Greeting.tsx
import React from 'react';
import { View, Text } from 'react-native';

interface GreetingProps {
  name: string;
}

const Greeting: React.FC<GreetingProps> = ({ name }) => (
  <View>
    <Text>Hello, {name}!</Text>
  </View>
);

export default Greeting;
```

* **`interface` or `type`**: Defines the shape of the props object.
* **`React.FC`**: Specifies that the component is a functional component, automatically inferring the return type as `ReactElement`.

#### **Typing State**

React Native components that manage internal state can also use TypeScript to type the state object.

```tsx
// Counter.tsx
import React, { useState } from 'react';
import { View, Text, Button } from 'react-native';

const Counter: React.FC = () => {
  const [count, setCount] = useState<number>(0);

  return (
    <View>
      <Text>Count: {count}</Text>
      <Button title="Increment" onPress={() => setCount(count + 1)} />
    </View>
  );
};

export default Counter;
```

* **`useState<number>(0)`**: Here, `number` specifies that the state will hold a number value.

#### **Typing Navigation (React Navigation)**

If you are using **React Navigation**, you can also type the navigation parameters and route names.

For example, in a stack navigator, you can type the navigation prop and route parameters.

```tsx
// HomeScreen.tsx
import React from 'react';
import { View, Text, Button } from 'react-native';
import { StackScreenProps } from '@react-navigation/stack';

type RootStackParamList = {
  Home: undefined;
  Details: { userId: string };
};

type HomeScreenProps = StackScreenProps<RootStackParamList, 'Home'>;

const HomeScreen: React.FC<HomeScreenProps> = ({ navigation }) => {
  return (
    <View>
      <Text>Home Screen</Text>
      <Button
        title="Go to Details"
        onPress={() => navigation.navigate('Details', { userId: '123' })}
      />
    </View>
  );
};

export default HomeScreen;
```

* **`StackScreenProps`**: Provides type safety for navigation and route parameters.
* **`RootStackParamList`**: Defines the routes and their parameters in the stack.

---

### 🟡 **3. Type-safe Redux & API Responses**

TypeScript can help ensure that the data you're working with is correctly typed, whether it’s in Redux or from API responses.

#### **Type-safe Redux**

When working with Redux, it’s important to define the state shape and action types to ensure type safety.

1. **Defining Redux Slice with Redux Toolkit:**

```tsx
// userSlice.ts
import { createSlice, PayloadAction } from '@reduxjs/toolkit';

interface UserState {
  id: string | null;
  name: string | null;
}

const initialState: UserState = {
  id: null,
  name: null,
};

const userSlice = createSlice({
  name: 'user',
  initialState,
  reducers: {
    setUser(state, action: PayloadAction<UserState>) {
      state.id = action.payload.id;
      state.name = action.payload.name;
    },
  },
});

export const { setUser } = userSlice.actions;
export default userSlice.reducer;
```

2. **Typing Dispatch and Selector:**

```tsx
// store.ts
import { configureStore } from '@reduxjs/toolkit';
import userReducer from './userSlice';

const store = configureStore({
  reducer: {
    user: userReducer,
  },
});

export type RootState = ReturnType<typeof store.getState>;
export type AppDispatch = typeof store.dispatch;
export default store;
```

* **`PayloadAction<UserState>`**: Ensures that the action’s payload matches the expected type.
* **`RootState`**: Defines the shape of the entire Redux store.

#### **Type-safe API Responses**

When working with APIs, you can define types for the expected API responses.

```tsx
// api.ts
import axios from 'axios';

interface User {
  id: string;
  name: string;
}

export const fetchUserData = async (userId: string): Promise<User> => {
  const response = await axios.get(`https://api.example.com/user/${userId}`);
  return response.data;
};
```

* **`Promise<User>`**: Ensures that the function returns a `User` object wrapped in a promise.

#### **Handling API Data in Components**

You can type the API data when fetching it and ensure that the component correctly uses the expected shape.

```tsx
// UserProfile.tsx
import React, { useEffect, useState } from 'react';
import { View, Text } from 'react-native';
import { fetchUserData } from './api';

interface User {
  id: string;
  name: string;
}

const UserProfile: React.FC<{ userId: string }> = ({ userId }) => {
  const [user, setUser] = useState<User | null>(null);

  useEffect(() => {
    const getUser = async () => {
      const data = await fetchUserData(userId);
      setUser(data);
    };

    getUser();
  }, [userId]);

  return (
    <View>
      {user ? <Text>{user.name}</Text> : <Text>Loading...</Text>}
    </View>
  );
};

export default UserProfile;
```

* **`User | null`**: Ensures that the `user` state can either be of type `User` or `null` (before data is loaded).

---

### 🔴 **4. Conclusion**

Using TypeScript in a React Native project brings many benefits, including:

* Type safety for props, state, navigation, Redux, and API responses.
* Early error detection at compile time.
* Better tooling and developer experience with auto-completion and documentation.

To maximize the benefits of TypeScript in React Native:

* **Type all your props and state**: Ensure that all props and state are typed to prevent errors.
* **Use type-safe navigation**: Leverage React Navigation's built-in TypeScript support for route parameters and navigation actions.
* **Leverage TypeScript with Redux**: Use Redux Toolkit and type your slices and actions for better maintainability.
* **Type your API responses**: Make sure API data is typed to catch errors when dealing with external data sources.

### 🟡 **17. Authentication & Security**

Authentication and security are critical components of mobile app development. In this section, we’ll cover popular methods for user authentication, including Firebase Authentication, OAuth, token-based authentication using JWT, and more advanced security practices like secure storage and biometric authentication.

---

### 🔲 **1. Firebase Authentication / OAuth Providers**

Firebase Authentication provides an easy-to-implement solution for authenticating users using a variety of methods such as email/password, social media logins (Google, Facebook, Twitter), and more. OAuth providers are used to allow users to authenticate via third-party services (e.g., Google, Facebook, etc.).

#### **Setting Up Firebase Authentication**

To use Firebase Authentication, follow these steps:

1. **Install Firebase dependencies:**

```bash
npm install @react-native-firebase/app @react-native-firebase/auth
```

2. **Configure Firebase in your app:**

Go to the [Firebase console](https://console.firebase.google.com/), create a new project, and enable the authentication methods you need.

* For email/password login, enable the "Email/Password" sign-in method.
* For Google or Facebook login, enable the respective sign-in methods and configure the OAuth credentials.

3. **Firebase Email/Password Authentication:**

```tsx
import React, { useState } from 'react';
import { View, TextInput, Button, Text } from 'react-native';
import auth from '@react-native-firebase/auth';

const SignUpScreen: React.FC = () => {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');

  const handleSignUp = async () => {
    try {
      await auth().createUserWithEmailAndPassword(email, password);
      console.log('User account created');
    } catch (error) {
      console.error(error.message);
    }
  };

  return (
    <View>
      <TextInput
        placeholder="Email"
        value={email}
        onChangeText={setEmail}
      />
      <TextInput
        placeholder="Password"
        secureTextEntry
        value={password}
        onChangeText={setPassword}
      />
      <Button title="Sign Up" onPress={handleSignUp} />
    </View>
  );
};

export default SignUpScreen;
```

4. **OAuth Authentication (Google Sign-in example):**

```tsx
import React from 'react';
import { Button, View } from 'react-native';
import auth from '@react-native-firebase/auth';
import { GoogleSignin } from '@react-native-google-signin/google-signin';

GoogleSignin.configure({
  webClientId: 'YOUR_GOOGLE_WEB_CLIENT_ID', // from Firebase console
});

const GoogleSignIn: React.FC = () => {
  const handleGoogleSignIn = async () => {
    try {
      const { idToken } = await GoogleSignin.signIn();
      const googleCredential = auth.GoogleAuthProvider.credential(idToken);
      await auth().signInWithCredential(googleCredential);
      console.log('Signed in with Google');
    } catch (error) {
      console.error(error.message);
    }
  };

  return (
    <View>
      <Button title="Sign in with Google" onPress={handleGoogleSignIn} />
    </View>
  );
};

export default GoogleSignIn;
```

* **Firebase Authentication** is a secure, easy-to-implement solution for mobile app authentication, handling various login methods.
* **OAuth** providers like Google and Facebook enable users to authenticate with their existing social media accounts, improving user experience.

---

### 🔴 **2. Token-Based Authentication (JWT)**

JWT (JSON Web Token) is a compact, URL-safe method for securely transmitting information between a client and a server. In a typical use case, the server generates a token after the user successfully logs in, and the client stores it for subsequent requests.

#### **JWT Authentication Flow**

1. **Login & Get JWT Token:**

On successful login (using Firebase, OAuth, or custom backend), the backend generates a JWT and sends it to the client.

```tsx
// Example of sending a login request from React Native app
const handleLogin = async (email: string, password: string) => {
  const response = await fetch('https://your-api.com/login', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ email, password }),
  });
  const data = await response.json();
  const token = data.token; // JWT token
  // Store token securely
  storeToken(token);
};
```

2. **Storing JWT securely using AsyncStorage or SecureStore:**

```tsx
import * as SecureStore from 'expo-secure-store';

const storeToken = async (token: string) => {
  await SecureStore.setItemAsync('userToken', token);
};
```

3. **Making Authenticated Requests with JWT:**

```tsx
const getUserData = async () => {
  const token = await SecureStore.getItemAsync('userToken');
  const response = await fetch('https://your-api.com/user', {
    headers: { Authorization: `Bearer ${token}` },
  });
  const data = await response.json();
  console.log(data);
};
```

4. **Logging Out (Clear JWT):**

```tsx
const handleLogout = async () => {
  await SecureStore.deleteItemAsync('userToken');
  console.log('Logged out');
};
```

* **JWT** is a secure way to authenticate users for subsequent requests. It avoids the need to store sensitive session data on the server.
* **Secure Storage**: Use `expo-secure-store` or libraries like `react-native-keychain` to securely store sensitive tokens.

---

### 🟡 **3. Secure Storage**

Secure storage is essential to store sensitive data like tokens, user credentials, and session data in a secure and encrypted manner.

#### **Using SecureStore (Expo)**

```tsx
import * as SecureStore from 'expo-secure-store';

// Store data securely
const storeSecureData = async (key: string, value: string) => {
  await SecureStore.setItemAsync(key, value);
};

// Retrieve stored data securely
const getSecureData = async (key: string) => {
  const value = await SecureStore.getItemAsync(key);
  return value;
};

// Delete stored data
const deleteSecureData = async (key: string) => {
  await SecureStore.deleteItemAsync(key);
};
```

#### **React Native Keychain**

For non-Expo projects, `react-native-keychain` is another option for securely storing sensitive data:

```bash
npm install react-native-keychain
```

```tsx
import * as Keychain from 'react-native-keychain';

// Store a password
await Keychain.setGenericPassword('user', 'password');

// Retrieve the password
const credentials = await Keychain.getGenericPassword();
console.log(credentials);

// Delete credentials
await Keychain.resetGenericPassword();
```

* **Secure storage** is crucial for storing sensitive information like JWT tokens or user credentials. Both `expo-secure-store` and `react-native-keychain` offer encryption to ensure that the data is stored safely.

---

### 🔴 **4. Biometric Authentication**

Biometric authentication allows users to authenticate via fingerprint, facial recognition, or other biometric methods. This adds an extra layer of security for user authentication.

#### **Using `react-native-biometrics`**

You can use `react-native-biometrics` to integrate biometric authentication into your app:

1. **Install Dependencies:**

```bash
npm install react-native-biometrics
```

2. **Check if Biometric Authentication is Available:**

```tsx
import React, { useState } from 'react';
import { Button, View, Text } from 'react-native';
import ReactNativeBiometrics from 'react-native-biometrics';

const BiometricsExample: React.FC = () => {
  const [result, setResult] = useState('');

  const handleBiometricAuth = async () => {
    try {
      const { available } = await ReactNativeBiometrics.isSensorAvailable();
      if (available) {
        const { success, error } = await ReactNativeBiometrics.simplePrompt({
          promptMessage: 'Confirm your identity',
        });
        if (success) {
          setResult('Authentication Successful');
        } else {
          setResult(`Authentication Failed: ${error}`);
        }
      } else {
        setResult('Biometrics not available');
      }
    } catch (error) {
      setResult(`Error: ${error}`);
    }
  };

  return (
    <View>
      <Button title="Authenticate with Biometrics" onPress={handleBiometricAuth} />
      <Text>{result}</Text>
    </View>
  );
};

export default BiometricsExample;
```

* **Biometric authentication** improves security and enhances the user experience by providing an alternative authentication method to passwords.

---

### 🟡 **5. Conclusion**

Authentication and security in React Native apps can be achieved with various methods, each with its own strengths and use cases.

* **Firebase Authentication / OAuth**: Ideal for handling user sign-ins via email/password or social logins like Google and Facebook.
* **Token-based Auth (JWT)**: Provides secure and stateless authentication between the client and server.
* **Secure Storage**: Protects sensitive data like JWT tokens using secure storage libraries (e.g., SecureStore, react-native-keychain).
* **Biometric Authentication**: Adds an additional layer of security by allowing users to authenticate using their fingerprint or face.

### 🟡 **18. CI/CD & App Deployment**

Continuous Integration (CI) and Continuous Deployment (CD) are essential for automating the process of building, testing, and deploying your React Native app. This section will guide you through the process of building and submitting your app to the App Store and Google Play Store, as well as integrating CI/CD pipelines to streamline your development workflow.

---

### 🔲 **1. Android & iOS Builds (APK, AAB, IPA)**

Before deploying your app to the App Store or Play Store, you need to generate build files (APK/AAB for Android, IPA for iOS).

#### **Android Build**

1. **Generate APK or AAB for Android:**

To create an APK (Android Package) or AAB (Android App Bundle), use the following command in your React Native project:

```bash
# For APK (debug)
npx react-native run-android --variant=release

# For AAB (Android App Bundle, recommended for Play Store)
cd android
./gradlew bundleRelease
```

* **APK**: APK is the traditional Android app file, suitable for manual distribution.
* **AAB**: AAB is the preferred format for the Google Play Store as it optimizes the app size for various devices.

2. **Signing the APK/AAB:**

To sign your APK/AAB, you'll need a keystore file. If you don’t have one, you can generate it:

```bash
keytool -genkeypair -v -keystore my-release-key.keystore -keyalg RSA -keysize 2048 -validity 10000 -alias my-key-alias
```

In your `android/app/build.gradle` file, add the keystore information:

```gradle
android {
    signingConfigs {
        release {
            storeFile file('<path_to_your_keystore_file>')
            storePassword '<your_store_password>'
            keyAlias '<your_key_alias>'
            keyPassword '<your_key_password>'
        }
    }

    buildTypes {
        release {
            signingConfig signingConfigs.release
        }
    }
}
```

3. **Build the APK/AAB:**

Once your keystore is configured, build the APK/AAB:

```bash
# To build APK
cd android
./gradlew assembleRelease

# To build AAB
cd android
./gradlew bundleRelease
```

#### **iOS Build**

1. **Generate IPA for iOS:**

To generate an IPA file for iOS, you need to run the following command:

```bash
npx react-native run-ios --configuration Release
```

Or, use Xcode for more control over the build process.

2. **Code Signing for iOS:**

iOS builds require provisioning profiles and certificates. These can be created in the Apple Developer Portal.

* **Certificates**: Create an iOS Distribution Certificate for your app.
* **Provisioning Profile**: Create a Distribution Provisioning Profile that matches your app’s Bundle ID and certificate.

Once the profiles are created, use Xcode to manage the signing process or set up `fastlane` for automating signing.

---

### 🔴 **2. App Store / Play Store Submission**

#### **Google Play Store Submission**

1. **Create a Google Play Developer Account**: You’ll need a developer account to publish your app on the Play Store. Visit the [Google Play Console](https://play.google.com/console) to register.

2. **Create a New App**: Go to the Play Console, click “Create Application,” and fill in the necessary details (app title, description, screenshots, etc.).

3. **Upload the AAB**: Once your AAB is ready, upload it to the Play Console in the "Release" section.

4. **Set Up Pricing and Distribution**: Choose the countries where your app will be available and set a price (if applicable).

5. **Review and Submit**: After filling out all the required information, submit your app for review. Google will check your app for any policy violations before it gets published.

#### **Apple App Store Submission**

1. **Create an Apple Developer Account**: You’ll need an Apple Developer account to publish your app. Visit the [Apple Developer Portal](https://developer.apple.com/) to enroll.

2. **Prepare for Submission**: Use Xcode to upload the IPA file to App Store Connect.

3. **App Store Connect**: Log in to [App Store Connect](https://appstoreconnect.apple.com/), create a new app, and fill in the necessary details (description, screenshots, app category, etc.).

4. **Submit for Review**: Once all information is filled out, submit your app for Apple’s review. Apple will assess your app based on guidelines, and once approved, it will be available in the App Store.

---

### 🟡 **3. Code Signing, Certificates & Profiles**

#### **Code Signing (Android)**

* For Android, you need a **keystore** file to sign your app before publishing it to the Play Store.
* The signing configuration is specified in `android/app/build.gradle`.

#### **Code Signing (iOS)**

* For iOS, you need to configure your **Apple Developer Certificates** and **Provisioning Profiles** to sign your app.
* Xcode can handle most of the signing process for you, but you may need to manage profiles in the [Apple Developer Portal](https://developer.apple.com/).

---

### 🔲 **4. Using EAS (Expo Application Services)**

**EAS** is Expo's set of services that streamline app building, updating, and deployment. It automates the app building process, making it easy to create builds without having to manually handle Android/iOS configurations.

#### **EAS Build Setup**

1. **Install EAS CLI:**

```bash
npm install -g eas-cli
```

2. **Configure EAS:**

Login to EAS:

```bash
eas login
```

Run `eas build` for either iOS or Android:

```bash
eas build --platform ios
eas build --platform android
```

EAS will automatically handle code signing and app building for you.

3. **Submit to the App Store/Play Store:**

Once your build is ready, use the Expo Dashboard or EAS CLI to submit your app directly to the respective app stores.

---

### 🟡 **5. CI/CD with GitHub Actions, Bitrise, or Fastlane**

Automating your build, test, and deployment process using **CI/CD** pipelines will help maintain consistency and reduce errors. Here are some popular tools for setting up CI/CD:

#### **GitHub Actions**

1. **GitHub Actions Setup:**

Create a `.github/workflows` directory and add a workflow YAML file for the build process.

```yaml
name: React Native CI/CD

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: macos-latest

    steps:
    - uses: actions/checkout@v2
    - name: Set up Node.js
      uses: actions/setup-node@v2
      with:
        node-version: '14'
    - name: Install dependencies
      run: npm install
    - name: Build Android APK
      run: cd android && ./gradlew assembleRelease
    - name: Build iOS IPA
      run: npx react-native run-ios --configuration Release
```

This example workflow automatically builds your app on every push to the `main` branch.

2. **CI/CD Pipeline with GitHub Actions**: GitHub Actions allows seamless integration with your React Native app’s build and deployment process.

#### **Bitrise**

Bitrise is a CI/CD platform designed for mobile app development. It supports React Native builds and provides pre-configured workflows for Android and iOS.

1. **Sign up and Create a Bitrise Project**: Connect your GitHub repository and configure your build steps for Android and iOS.

2. **Bitrise Workflow**: You can customize workflows to include tests, builds, and deployments (to Google Play or App Store).

#### **Fastlane**

Fastlane automates tedious tasks such as screenshots, code signing, and release management for iOS and Android apps.

1. **Install Fastlane**:

```bash
gem install fastlane
```

2. **Fastlane Setup**:

Run `fastlane init` to set up your project.

3. **CI/CD Pipeline with Fastlane**: Create a `Fastfile` for your app's deployment pipeline. You can automate tasks like building, testing, and submitting your app.

```bash
fastlane android beta
fastlane ios release
```

---

### 🟡 **6. Conclusion**

With CI/CD tools and services, the process of building, testing, and deploying React Native apps becomes automated and streamlined:

* **Android/iOS Builds**: Generate APK, AAB, and IPA files for distribution.
* **App Store/Play Store Submission**: Submit your app with the appropriate configurations for each platform.
* **Code Signing & Certificates**: Proper code signing ensures security and compliance with platform requirements.
* **EAS Build**: Expo Application Services simplifies the build and deployment process.
* **CI/CD**: Automate the process using tools like GitHub Actions, Bitrise, or Fastlane for consistent app builds and deployments.

By adopting a CI/CD pipeline, you ensure a smoother and faster development and deployment workflow.

### 🟡 **19. Monorepos & Modularization (Optional)**

Monorepos and modularization are useful techniques for organizing large-scale applications, particularly when multiple teams are working on different parts of the app. This section will cover how to set up a monorepo structure in a React Native project and manage shared components and services.

---

### 🔲 **1. What is a Monorepo?**

A **Monorepo** (short for Monolithic Repository) is a software development strategy where multiple projects (such as React Native apps, backend services, and shared libraries) are stored in a single repository.

Benefits of using a monorepo:

* **Unified versioning**: All projects within the monorepo can be versioned and updated simultaneously.
* **Shared dependencies**: Centralized management of dependencies.
* **Improved code sharing**: Easy reuse of components and services across different parts of the app or even different apps.
* **Simplified CI/CD**: Unified build and test processes for all projects.

---

### 🔴 **2. Setting Up Monorepo with Lerna or Nx**

**Lerna** and **Nx** are popular tools for managing monorepos, with a focus on managing dependencies and simplifying workflows.

#### **Lerna Setup for React Native**

Lerna helps to manage the monorepo structure and versioning, which is particularly useful when dealing with multiple packages.

1. **Install Lerna**:

First, install Lerna globally:

```bash
npm install --global lerna
```

2. **Initialize Lerna**:

Create a new directory for the monorepo and initialize Lerna:

```bash
mkdir my-monorepo
cd my-monorepo
lerna init
```

This will create a `lerna.json` file and a `packages` directory. Each project (e.g., the React Native app or shared libraries) will go into the `packages` directory.

3. **Create Packages**:

Now, create multiple packages inside the `packages` directory. For example:

```bash
packages/
  my-app/
  shared-components/
  shared-services/
```

* **`my-app/`**: The main React Native app.
* **`shared-components/`**: A shared component library for UI components.
* **`shared-services/`**: A shared service library for things like API calls, data management, etc.

4. **Managing Dependencies**:

Lerna can link dependencies between your packages automatically.

```bash
lerna bootstrap
```

This will install dependencies and link local packages that are referenced in other packages.

5. **Running Scripts Across Packages**:

You can run scripts across multiple packages using Lerna:

```bash
lerna run build
```

This will run the `build` script in each package within the monorepo.

#### **Nx Setup for React Native**

Nx is a powerful toolkit for managing monorepos with advanced features like code generation, testing, and linting. It's particularly useful for larger teams and projects.

1. **Install Nx CLI**:

First, install Nx globally:

```bash
npm install -g nx
```

2. **Initialize Nx Workspace**:

Create a new Nx workspace with React Native support:

```bash
npx create-nx-workspace@latest my-monorepo
cd my-monorepo
```

Follow the prompts and choose a React Native app template.

3. **Add React Native to Nx**:

You can add React Native support to an existing Nx workspace:

```bash
nx g @nrwl/react-native:application my-app
```

This will generate a new React Native app within the monorepo.

4. **Managing Libraries**:

You can create shared libraries for components, utilities, and services:

```bash
nx g @nrwl/react-native:library shared-components
```

This creates a new library that can be shared across different apps within the monorepo.

5. **Running Commands with Nx**:

Nx provides a powerful task runner and cache mechanism. You can run builds, tests, and other tasks across the entire monorepo:

```bash
nx build my-app
```

Nx will cache previous runs, so subsequent builds are faster.

---

### 🔲 **3. Managing Shared Components and Services**

When using a monorepo, it's essential to structure your shared components and services in a way that allows easy access and reuse across different parts of the app.

#### **Shared Components**

1. **Create a Component Library**:

In your monorepo, create a package specifically for shared components. For example, `shared-components/`. In this package, you can have commonly used UI components like buttons, inputs, cards, etc.

Example structure:

```
packages/
  shared-components/
    src/
      Button.tsx
      Input.tsx
      Card.tsx
    package.json
    tsconfig.json
```

To use this component library in your main app (`my-app/`), you simply import the components like so:

```javascript
import { Button } from 'shared-components';
```

#### **Shared Services**

2. **Create a Service Library**:

You can also have a shared service library for API calls, state management, and utilities. For example, `shared-services/`.

Example structure:

```
packages/
  shared-services/
    src/
      api.ts
      auth.ts
    package.json
    tsconfig.json
```

In your React Native app (`my-app/`), you can import these services:

```javascript
import { api } from 'shared-services';
```

This structure allows you to centralize business logic, making it easier to maintain and update.

#### **Benefits of Modularization**

* **Code Reusability**: Components and services can be reused across different parts of your application or even across multiple apps.
* **Scalability**: Modularizing your app into smaller packages makes it easier to scale and maintain as your codebase grows.
* **Separation of Concerns**: Organizing your code into distinct modules for components, services, and utilities promotes a clean architecture.

---

### 🔴 **4. Managing Versioning and Publishing with Lerna**

Lerna helps you manage versions of your packages. If you need to update a shared component or service, Lerna makes it easy to update dependencies across the monorepo.

#### **Versioning with Lerna**

Lerna uses two versioning strategies:

* **Fixed Versioning**: All packages in the monorepo share the same version.
* **Independent Versioning**: Each package has its own version.

To publish updated packages, use:

```bash
lerna publish
```

Lerna will prompt you to select the version bump for each package and publish it to npm.

---

### 🟡 **5. Conclusion**

Monorepos are a powerful approach for managing large-scale applications, especially when you need to manage multiple projects (such as a React Native app, shared libraries, and backend services) in a single repository.

* **Lerna** and **Nx** are popular tools for managing monorepos, providing features like dependency management, code sharing, and advanced task running.
* By modularizing your codebase into reusable components and services, you can ensure a clean, scalable architecture that can grow with your app.
* **Versioning** and **publishing** shared packages is streamlined with Lerna, making it easy to maintain consistency across different parts of the app.

By adopting a monorepo structure and modularizing your code, you can enhance your development workflow and improve code maintainability in large-scale React Native projects.

### 🟡 **20. Advanced Libraries & Ecosystem**

As React Native applications grow in complexity, it becomes essential to integrate advanced libraries and tools to improve performance, state management, testing, and development workflow. This section will cover some of the most popular libraries in the React Native ecosystem.

---

### 🔲 **1. React Query / Tanstack Query**

**React Query** (now **Tanstack Query**) is a powerful library for managing server-state in React and React Native applications. It simplifies data fetching, caching, synchronization, and pagination.

#### **Key Features:**

* **Automatic Caching**: React Query automatically caches fetched data and reuses it across components.
* **Background Fetching**: Data is automatically refetched in the background to ensure that the app has up-to-date data.
* **Pagination and Infinite Scroll**: Built-in support for pagination and infinite scrolling with minimal setup.
* **Error Handling**: Built-in error and loading states for asynchronous queries.

#### **Installation and Setup**:

```bash
npm install @tanstack/react-query
```

#### **Usage Example**:

```javascript
import { useQuery } from '@tanstack/react-query';

const fetchPosts = async () => {
  const res = await fetch('https://jsonplaceholder.typicode.com/posts');
  return res.json();
};

const Posts = () => {
  const { data, error, isLoading } = useQuery(['posts'], fetchPosts);

  if (isLoading) return <Text>Loading...</Text>;
  if (error) return <Text>Error: {error.message}</Text>;

  return (
    <FlatList
      data={data}
      keyExtractor={(item) => item.id.toString()}
      renderItem={({ item }) => <Text>{item.title}</Text>}
    />
  );
};
```

---

### 🔲 **2. Zustand, Jotai, or Recoil (State Management)**

While Redux and Context API are the most common ways to manage state in React Native, **Zustand**, **Jotai**, and **Recoil** are alternatives that offer simpler, more flexible solutions for state management.

#### **Zustand**:

Zustand is a lightweight, fast, and minimalistic state management library that doesn’t require the use of a reducer.

**Installation**:

```bash
npm install zustand
```

**Usage Example**:

```javascript
import create from 'zustand';

const useStore = create((set) => ({
  count: 0,
  increment: () => set((state) => ({ count: state.count + 1 })),
}));

const Counter = () => {
  const { count, increment } = useStore();
  return (
    <View>
      <Text>{count}</Text>
      <Button title="Increment" onPress={increment} />
    </View>
  );
};
```

#### **Jotai**:

Jotai is another minimal state management library that provides atomic state management. It allows you to create independent units of state that can be shared across components.

**Installation**:

```bash
npm install jotai
```

**Usage Example**:

```javascript
import { atom, useAtom } from 'jotai';

const countAtom = atom(0);

const Counter = () => {
  const [count, setCount] = useAtom(countAtom);
  return (
    <View>
      <Text>{count}</Text>
      <Button title="Increment" onPress={() => setCount(count + 1)} />
    </View>
  );
};
```

#### **Recoil**:

Recoil is a state management library for React and React Native that offers a more flexible and scalable alternative to React’s Context API.

**Installation**:

```bash
npm install recoil
```

**Usage Example**:

```javascript
import { atom, useRecoilState } from 'recoil';

const countState = atom({
  key: 'countState', 
  default: 0,
});

const Counter = () => {
  const [count, setCount] = useRecoilState(countState);
  return (
    <View>
      <Text>{count}</Text>
      <Button title="Increment" onPress={() => setCount(count + 1)} />
    </View>
  );
};
```

---

### 🔲 **3. Detox for End-to-End Testing**

**Detox** is an end-to-end testing framework for React Native that allows you to test your mobile application in a real-world environment. It helps automate interactions with the app and verify its functionality.

#### **Key Features:**

* **Automated End-to-End Testing**: Automates user flows like tapping buttons, typing in inputs, and verifying the UI.
* **Real Device Testing**: Runs tests on real devices or emulators/simulators, providing more accurate results.
* **Cross-Platform Support**: Supports both iOS and Android.

#### **Installation and Setup**:

```bash
npm install detox --save-dev
```

1. Set up Detox in your project by initializing the configuration:

```bash
detox init -r jest
```

2. Create a test file and write your tests:

```javascript
describe('Example App', () => {
  it('should show the welcome screen', async () => {
    await expect(element(by.id('welcome-screen'))).toBeVisible();
  });

  it('should navigate to the next screen', async () => {
    await element(by.id('next-button')).tap();
    await expect(element(by.id('next-screen'))).toBeVisible();
  });
});
```

3. Run the tests:

```bash
detox test
```

---

### 🔲 **4. Storybook for Component Development**

**Storybook** is an open-source tool for developing UI components in isolation. It allows you to visualize and test components outside of the app, making the development process smoother.

#### **Key Features:**

* **Component Isolation**: Develop and test UI components in isolation from the app.
* **UI Documentation**: Generate interactive documentation for your components.
* **Easy Integration**: Integrates well with React Native and web projects.

#### **Installation and Setup**:

```bash
npx -p @storybook/cli sb init --type react_native
```

#### **Usage Example**:

Create a simple button component:

```javascript
import React from 'react';
import { TouchableOpacity, Text } from 'react-native';

const Button = ({ onPress, title }) => (
  <TouchableOpacity onPress={onPress}>
    <Text>{title}</Text>
  </TouchableOpacity>
);

export default Button;
```

Now, create a story for the button:

```javascript
import React from 'react';
import { storiesOf } from '@storybook/react-native';
import Button from './Button';

storiesOf('Button', module).add('default', () => (
  <Button title="Click Me" onPress={() => alert('Button Pressed!')} />
));
```

To run Storybook, start the React Native app with:

```bash
npm run storybook
```

---

### 🟡 **5. Conclusion**

Integrating advanced libraries and tools into your React Native app can significantly improve your development workflow, enhance performance, and simplify state management and testing.

* **React Query (Tanstack Query)**: Efficient data fetching and caching with automatic synchronization.
* **State Management Libraries**: Tools like **Zustand**, **Jotai**, and **Recoil** provide more flexible, lightweight alternatives to Redux for managing app state.
* **Detox**: A robust end-to-end testing framework to ensure your app works as expected in real environments.
* **Storybook**: A great tool for developing and testing components in isolation, improving UI consistency and documentation.

By leveraging these tools, you can build more maintainable, testable, and efficient React Native applications.








