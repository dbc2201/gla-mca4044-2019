# Mobile Application Development MCA4044

## Sample Solutions for Mid-Sem 1 Exam



## Section - A

### Question 1

#### List the steps to initialize a Git repository inside any Android Studio Project.

### Answer 1

The following are the steps to initialize a Git repository inside any Android Studio project-

1. Open an existing Android Studio project or create a new one.
2. Click on 'VCS' menu tab from the menu bar.
3. Select the option that says 'Import Into Version Control' in the context menu.
4. Select the option that says 'Create Git Repository' in the context menu.
5. A prompt will open up with the path to your workspace, click on the button that has the logo of Android Studio, doing this will select the current project directory.
6. Click 'OK' to finish.
7. There will be a 'Git-master' label in the bottom right hand corner of Android Studio IDE to indicate Git has been initialized for your current project.



------



### Question 2

#### Explain the term ‘UI’ in context of Mobile Application Development.

### Answer 2

UI is the abbreviation for 'User Interface'. A User Interface or *UI* for short is the medium through which a user can interact with any machine (or more specifically computer). We create UIs to allow the user to interact with a computer to yield results that are relevant to them. The most common example of an UI would be a GUI or 'Graphical User Interface'. You might see them in your OS (Operating System), you have been given a playground with graphically assisted interface that gives you a real time feed back of the events that occur due to your interaction, this makes it easier for any user be able to get started quickly. We generally say, the better the UI, the better the software, although, that is  ***not always*** the case.

In the context of Mobile Application Development, the UI is the contents of the screen that a user sees on her device, it may be anything ranging from a complex myriad of dynamically generated layout and widgets to anything as simple as a static single button. In Android, we call them 'Activities', they render the contents of the screen and define their behaviour when a user interacts with them. The UI for a mobile device differs greatly from a conventional UI for a computer since the real estate (the screen size) of a mobile device is much much smaller than that of a computer and we have to keep that in consideration while developing apps. Also, not all the mobile devices have same screen sizes or even the same configurations for that matter which in turns affects our UIs greatly.



------



### Question 3

#### Explain the term ‘mobility’. How does it affect software development process?

### Answer 3

Mobility means the ability of an entity to move about freely. Mobility in terms of mobile application development means the ability of the target mobile device to move about while the app still runs on it. It may have great consequences on the app in terms of the app's performance.

For ex, an app that heavily relies on a stable internet connection would stutter when the target mobile device is on a move and unable to capture network packets smoothly. 

This, in turn, becomes the job of the software developer to ensure that the target mobile device's mobility should not or as little as hinder the performance of the app. The software development process needs to put in allowances for the mobility of the target device in their requirement gathering as well as feasibility stages thus altering the whole process in a 'snowball effect'. The actual developer needs to put in measure such that the user can at least be notified of any ramifications of the mobility of the target device on the app's performance, if not completely handling them at the business logic level.



------



## Section - B

### Question 1

#### Android Studio automatically creates two files for you when you create a new activity. Name the files and mention the differences between the two in terms of their usage. What are the languages used in both?

### Answer 1

The two files automatically created by Android Studio are -

1. ActivityName.java
2. activity_name.xml

- The `ActivityName.java` file is the business logic of our 'activity'. It defines the behaviour of the UI of the activity when a user interacts with it. It may also define data structures / databases / helper methods that facilitate the actual business logic of the app. It may sometimes also be used for dynamically generating UIs.

- The `activity_name.xml` file is the user interface for our 'activity'. It specifies the contents of our screen, what goes where and how does everything look. This file will define the basic look and feel of our 'Android Activity' which we can modify later on through our business logic.

The first file uses `Java` code inside it, while it is not actually *pure* Java code, it has the same syntax and semantics. The general behaviour of Java programming has been borrowed because of its strong user base, robustness and quick implementation via JVMs. It has most of the Java class supported inside it out of the box, which depends on the type of JDK used for development. Android Studio uses OpenJDK by default which has, *more of less*, the same implementation as the OracleJDK. Android also supports the OOP paradigm of Java programming and heavily relies on it for efficient and fast app development.

The second file uses `XML` code instead of `Java` to define the structure of the UI of our activity. This file states all the widgets that are to be rendered on the screen when the application is run, it is only when a *view* is rendered on the screen its behaviour can be controlled. Although the widgets can be specified through the `Java` class, it is advisable to create the skeletal structure from the `XML` layout resource file.



------



### Question 2

#### What are layouts? Compare and contrast a ‘Parent’ and a ‘Child’ in a layout. Discuss a few layouts that you use in Android Application Development along with their characteristics.

### Answer 2

A layout defines the visual structure for a user interface, such as the UI for an activity. You can declare a layout in two ways:

- Declare UI elements in `XML`. Android provides a straightforward `XML` vocabulary that corresponds to the View classes and subclasses, such as those for widgets and layouts.
- Instantiate layout elements at runtime. Your application can create View and ViewGroup objects (and manipulate their properties) programmatically using `Java`.

For example, you could declare your application's default layouts in XML, including the screen elements that will appear in them and their properties. You could then add code in your application that would modify the state of the screen objects, including those declared in XML, at run time.

The advantage to declaring your UI in XML is that it enables you to better separate the presentation of your application from the code that controls its behavior.

Using Android's XML vocabulary, you can quickly design UI layouts and the screen elements they contain, in the same way you create web pages in HTML — with a series of nested elements.

A *Parent* is an `XML` view that houses on or more views inside it, called a '*child*'. A *child* view is the direct successor of any parent, a child view can also be a parent to other views hence continuing the relationship.  We generally use Android specific layouts as '*parents*' in a layout resource file. They are separated on the basis of how they organize the *child* views inside it. Some of the most common examples are - 

1. ConstraintLayout - A group of child views using anchor points, edges, and guidelines to control how views are positioned relative to other elements in the layout. ConstraintLayout was designed to make it easy to drag and drop views in the layout editor.
2. LinearLayout - A group of child views positioned and aligned horizontally or vertically.
3. RelativeLayout - A group of child views in which each view is positioned and aligned relative to other views within the view group. In other words, the positions of the child views can be described in relation to each other or to the parent view group.
4. ScrollView - A group of child view that possess the ability to provide a scrolling animation when rendered on a small screen.

------



### Question 3

#### Compose the Java code to set an 'onClickListener()' method on a button. Inside the method, use a 'Toast' to signal the user that the button has been pressed. Examine the number of times the user has pressed the button and show it inside the toast. For ex – If the user pressed the button 10 times, then show - you have pressed the button 10 times!. Hint: use an int variable.

### Answer 3

```java
Button button = findViewById(R.id.button);

int counter = 0;

button.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        counter++;
        Toast.makeText(MainActivity.this, "You have pressed the button " + counter + " times.", Toast.LENGTH_SHORT).show();
    }
});
```

The whole code for this activity is written [here](https://gist.github.com/dbc2201/8be8f17aa2eb6efa4e3ba8e7c11b5dad).

------

