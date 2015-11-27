##How to Create and Test Your Own Cocoapods Project
# 
Recently I have open-sourced my project[TCTitleLoading](https://github.com/TravelC/TCTitleLoading)  and made it  supporting Cocoapods. Below is the procedure.

###1. Create Your Project and Submit It to Github

Create your project and submit it to Github，Record the address for later useage, for example：https://github.com/TravelC/TCTitleLoading.git

###2. Create a Branch for Cocoapods
Create a branch for Cocoapods. Naming it with version number is recommended, e.g.‘0.0.1’

###3. Create podspec File and Edit

Open Terminal, cd to your project directory, type command ‘pod spec create’to create a podspec file：

```
pod spec create test
```
'test' is the name of podspec file, you can change to any other name you like.

Once the file is created, you can edit it with your favourite text editor. There are detailed comments in the podspec file; just go through it and change it to what you need. Please take note that the final file should not contain any comment, so delete all the comments.

###4. Verify podspec File
Open Terminal, cd to the directory of your podspec file, type command  ‘pod spec lint ’ to verify it：

```
pod spec lint test.podspec
```

If the verification passes, the Terminal will print:
```
xxx passed validation.
```
If there's any issue, it will also print; just fix them and verify again. If you want to ignore the warnings，you can add --allow-warnings paramater to the command，for example：

```
pod spec lint test.podspec --allow-warnings
```

###5. Testing
When the verification is passed, you can test your Cocoapods project locally. Create a new project, create the pod file as usual, and add the pod with format like below:

```
pod "TCTitleLoading", :path => '../../TCTitleLoading'
```
what followed 'path =>' is the path of your Cocoapods project。

run conmmand ‘pod install’ in Terminal and continue your testing。

###6. Submit the Project to Cocoapods Trunk, So That Others Can Use your Library

If you have finished your tesing, you can now submit the project to Cocoapods trunk. If you haven't registed yet, you need to regist first. In Terminal, run command：

```
pod trunk register email 'name' --description='some description'
```

Since there's no password for the registeration which is related to you computer, I recommend that you write something about your computer for the description part, for example：‘Persional MacBook Pro’.

After registeration type 'pod lib lint' and hit enter:

```
pod lib lint

```
This will do the verification again，you can add --allow-warnings at the end to skip warnings：

```
pod lib lint --allow-warnings
```

After passed the verification, type and excute

```
pod trunk push TCTitleLoading.podspec --allow-warnings
```
the --allow-warnings paramater is optional.

If everything is OK, now your library is public in Cocoapods trunk. Give Cocoapods some time to index, do a 'pod search', Bingo!




