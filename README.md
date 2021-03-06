#Debug Build

We are proud to offer debug build for PhoneGap Build users. This service enables users to debug and interactively modify their applications during runtime; this new addition offers similar functionality to those found in Firebug and Google Chrome Inspector, which serve as an indispensable tool to developers working on web based projects. And now debug build provides the same benefits for PhoneGap developers.

----

## Sections

1. [Configuring A project to use Build](#project_build)
    1. [New Application](#new_build_project)
    2. [Existing Application](#existing_build_project)
2. [Running Debug Mode](#running_debug_mode)
    1. [Elements](#running_debug_mode_elements)
    2. [Console](#running_debug_mode_console)
3. [Example Use Case](#example_use_case)
4. [Closing Remarks](#closing_remarks)

---

<a id="project_build"></a>
##Configuring A Project to use Build

Build can be configured on either of the two cases.

<a id="new_build_project"></a>
###1.) New Application

After logging in Navigate to [https://build.phonegap.com/](https://build.phonegap.com/), and click the "new app" button.

![alt new app button](../images/create_app.jpg)

Next to enable debug mode select the "enable debugging"

![alt new app button](../images/enable_debug_new.jpg)

There you have it! Every build from this point will enable you to debug through PhoneGap Debug Build. To disable debug in the future simply unselect the "enable debugging" option from the application edit page (as seen in the section below) and save your changes.

<a id="existing_build_project"></a>
###2.) Existing Application

After logging in navigate to [https://build.phonegap.com/apps](https://build.phonegap.com/apps), and click the application you wish to enable debug on. 

The page just navigated to displays information useful to the status of your builds, and general information regarding the application. Click the "Edit" button in the top right hand corner and you will be presented with a page like the following:

![alt edit app page](../images/edit.jpg)

From this page we will enable debug build by ticking "enable debugging", then to save changes made to the application simply click "Save"; and there you have it! Every build from this point will enable you to debug through PhoneGap Debug Build. To disable debug in the future simply unselect the "enable debugging" option and save your changes.

---
<a id="runnin_debug_mode"></a>
##Running Debug Mode

To run you application in debug mode navigate to https://build.phonegap.com/apps, select the appropriate link to download for you platform and run it on your device or emulator. Next in the top right hand corner next to "Edit" there is now another option "Debug" available, click this link and you will be taken to a page that includes the following options available at this time: elements, and console.

<a id="running_debug_mode_elements"></a>
###Elements:

This powerhouse tool enables you too modify the application in realtime; a handy feature when making minor modifications or bug fixes on the fly. Example use cases could be editing the javascript to correct errors, modifying css styling, or editing the html.
<a id="running_debug_mode_console"></a>
###Console:

Another exciting feature that allows you to view debug output and interact with the javascript. Example use cases include bug tracking, and view application log output in realtime.

---
<a id="example_use_case"></a>
##Example Use Case


Walking through this demonstration will enable you to get a better understanding of the possible work flow in debug.  
   
You may download this sample application "Hello Debugging World" from:  
[https://github.com/hardeep/PhoneGap-Build-Debug](https://github.com/hardeep/PhoneGap-Build-Debug)

1.) Next create a new application on phonegap build with the contents of "Hello Debugging World"; for instructions on how to the former visit [https://build.phonegap.com/docs/git-hosting](https://build.phonegap.com/docs/git-hosting)

2.) Open the debug console and launch the newly built application on a device or simulator. You should now see you device listed under "Remote/Devices" (note You may need to refresh the page).

![alt edit app page](../images/connected.jpg)  

3.) To demonstrate some powerful debugging options, we have included JQuery to aid in our demonstration. Firstly you may wish to take a glance at the two sections we will mostly be looking at by clicking on the sections labeled "elements" and "console".

![alt edit app page](../images/elements.jpg)  

![alt edit app page](../images/console.jpg)  


4.) You may have realized that we have a typo in our header when we include phonegap.js. The Line should read.

    <script stype="text/javascript" scr="phonegap.js"></script> 

With out this interactive debugging session we would need to re-build our code, and deploy the it once again on the simulator or device; however we can remedy this error and continue with testing by simply using JQuery to dynamically import the required javascript file.

Go to the console and insert the following code.

    $.getScript('phonegap.js', function() { alert('Load was performed.'); })

Now if you take a look at the device or simulator we should have an alert that prompts us when PhoneGap has been loaded.

5.) We may now proceed to continue with our testing by calling "onLoad()" in the console which will fire up our application. You may notice that nothing has happened, this is because we have a typo in our html document. Modify the attribute id on the following line:

    <input type="button" id="buh_button" value="Check For Bugs">

to the following:

    <input type="button" id="bug_button" value="Check For Bugs">

6.) Now proceed to clicking the "Check for Bugs", at this point you should get an alert stating "Ya! No more bugs".

7.) As we have just demonstrated changing an attribute in the index.html page we can also change any other aspect of the html document such as the css. We can demonstrate by changing the class attribute on our "H1" from title1 to title2.

---
<a id="closing_remarks"></a>
##Closing Remarks:

This concludes the simple demonstration on live debugging, hopefully by now we have been able to demonstrate the time and effort saved through having such a feature.
