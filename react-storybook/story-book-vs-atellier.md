###Comparing react-storybook with react-atellier

----------

####react-storybook 
Idea here is to write down different scenarios/states of a component while development. ***https://github.com/kadirahq/react-storybook***

#####Benefits of using react-storybook:

 - **Development with scenarios :** Various behavior of a component can be captured as stories to be able to look back in future providing your own component library with multiple examples and reusable code.
 -**Documentation :** it has a very nice documentation to understand the thought process behind and helps you thru the installation and usage. 
 - **Active community :** The community is very actively contributing towards the development of react-storybook with more the 4000 follower in a very less time duration of 2 months. 
 - **Ease of use :** This module is found to be easier to configure based on the requirements for your development. Also the installation is hassle free and straight forward. 
 - **Promotes dev-documentation** :  The stories you write related to a component help to get an out of box documentation about your component with demo examples within the neat storybook UI of your own. 
 - **Push towards best practices :** helps you drive a thought process of building isolated functional components which are purely reusable. we found it helping with the practices like, 
	 - we should not pass class names/styles to a component as props. 
	 - the UI component should be dumb and should not have defined event handler coded inside the component, they should be passed as props.
 - **Supports covering edge Cases :** developing various stories for a component and having them preserved with your codebase helps you in covering more edge cases. 
 - **Runs on different server then your app**: its not active part of your application and runs on a different server all together. which keeps it isolated from your application to some extent. 
 - **Meaningful story writing :** It allows us to create meaningful stories, 
	 - features like `decorators` helps in contextual story writing. 
	 - basic prototype and behaviors can be visualized using `linkTo`. 
	 - `actions` are to mock the event handlers for components. 
 - **Configurations and Scaling :** react-storybook supports a wide range of configurations.
	 - it provides you to have an storybook specific webpack configuration along with storybook configuration. 
	 - supports loading of style variants css, scss, less etc. 
	 - Regular expressions to load multiple story files specific to components.

#####Improvements or further enhancements :
 - **Push towards test driven development(TDD) :** ideology can be further used to have it integrated with unit testing. where you write stories with unit tests to avoid redundancy and have same code for stories and unit tests. 
 - **Figuring out environment based setup :** In case we don't need our storybook to be active on other environment except development, we need figure out ways to disable it and prevent story files from loading. 
 - It will be great to have generator with storybook pre-integrated as a further enhancement. 

####react-atellier
Idea here is to pass your components to react-atellier which is going create and interactive UI for you to be able to configure the properties of a component and develop it. ***https://github.com/scup/atellier***
#####Benefits of using react-atellier:

 - **Neat and configurable UI :** Provides you a neat and configurable user interface for component out of box. 
 - **Interactions :** Easy to tweak the properties of a component and see the behavior it can have. 
 - **Runs on same server as of your app :** Its works on the same server as your app on a different route and you just need to pass the necessary components for it to populate. 

#####Improvements or further enhancements :

 - **Documentation is not very impressive :** Documentation is not very impressive which makes it harder on the installation and usage. 
 - **Community support :**  this is not as active and popular as react-storybook, lesser followers and rating. (800 over 4-5 months and no frequent updates)  
 - **Figuring out environment based setup :**  as react-atellier is more tightly coupled with  our application, we will always have to figure out the way to disable a route for other environments except development in case we don't want it be usable by the end users. 
 - **Less ease of use :** Debugging is hard as the error messaging is not very clear and poor documentation make is harder to user.
 - **Hard dependencies on propTypes of a component : ** you always need to have defined `propTypes` for a component as it is depended on generating the component properties and UI based on that. 
 - **No additional development :** Unlike react-storybook, there is no additional development needed. you only develop component as there is no concept of stories. 
 - **No support to dev documentation :** This is neutral towards dev documentation as we do not create stories for a component, we can only tweak them and see how the component behaves. 

####Conclusion 
To conclude, react-storybook seems a better option if we prefer to have good draft of documentation with examples along side development to be able to reuse what we have developed over time with a great support. On the other side, react-atellier is a neat and simple tool which can be considered for quick tweaks and short term goals. 
