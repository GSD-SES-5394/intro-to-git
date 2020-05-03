# Github Tutorial



## Create a github account

Go to https://github.com and sign up to create an account.

![image](https://user-images.githubusercontent.com/2446659/80923822-831cfc80-8d4b-11ea-9ed5-c78f256f42e3.png)

You may also need to confirm your email, and log in.


## Create a new Repository

While logged in to github, there should be a plus sign on the top right corner.

![image](https://user-images.githubusercontent.com/2446659/80923794-5832a880-8d4b-11ea-8d14-6427c96d73f2.png)

## Name your Repo

You can name it whatever you like, but don't put spaces or any funny characters like quote or slash. I would default to public unless this repo will have proprietary or secret information in it. 

![image](https://user-images.githubusercontent.com/2446659/80923912-ec047480-8d4b-11ea-957b-ec0d20838559.png)

Github can also put a README file in our repo for us to get us started. Check that box. Hit the create repository button to get started.

![image](https://user-images.githubusercontent.com/2446659/80924013-6503cc00-8d4c-11ea-8b46-0fd94092e13e.png)

Our landing page for our repo should look something like this.

![image](https://user-images.githubusercontent.com/2446659/80924066-9da3a580-8d4c-11ea-9c83-9de573da9b4f.png)

If you look at the address bar, you'll notice the pattern for github repos is 

`https://github.com/<USER NAME>/<REPO NAME>`

![image](https://user-images.githubusercontent.com/2446659/80924159-09860e00-8d4d-11ea-8985-07dba3d1f62c.png)


## Install Github Desktop

Git is a commandline application that you run from the terminal. Github also distributes an application called Github Desktop, which is a desktop application for Mac or Windows that may be a little easier to use. In my screenshots, I'll be using Windows, it will look a little different on a Mac, but it's fundamentally the same.

To download github desktop, go to https://desktop.github.com

![image](https://user-images.githubusercontent.com/2446659/80924456-a5fce000-8d4e-11ea-87ac-e9f2d22c2cdd.png)

Hit the download for windows button, run the installer and the application should launch automatically after installation completes.

![image](https://user-images.githubusercontent.com/2446659/80924509-03912c80-8d4f-11ea-9f86-11191c4d96d4.png)

Hit the button to sign into github.com

![image](https://user-images.githubusercontent.com/2446659/80924589-608ce280-8d4f-11ea-9cbe-b9b42d95e1e7.png)

enter in your user name and password, and finish logging in.

## Clone the Repo

Once you are logged in, you should be able to see your repos on the right hand side (at this point, there is probably only the one that we created).

![image](https://user-images.githubusercontent.com/2446659/80924650-c7120080-8d4f-11ea-9283-0314b57a8994.png)

Select your repo and on the bottom right corner there should be a button to clone that repo.

![image](https://user-images.githubusercontent.com/2446659/80924708-1b1ce500-8d50-11ea-80c1-b005b0d3934d.png)

Then it should ask you where you want to clone this repo to.

![image](https://user-images.githubusercontent.com/2446659/80924751-6800bb80-8d50-11ea-842e-d22f1171819f.png)

The Repository URL should look pretty similar to the URL of our repository landing page. You can change the local path if you have a preference where you would like these files to go. Otherwise, the defaults should all be fine.

After cloning completes, then you should see something like this.

![image](https://user-images.githubusercontent.com/2446659/80924844-0ee55780-8d51-11ea-9b14-ae07d549966e.png)

The top three buttons allow you to change the current repository, change the active branch, and to fetch origin. Fetching means to get any new information about the repo from the github server. Fetching doesn't change any files, it is always safe to fetch.

Github Desktop also has a place where it tells you which files have been modified, staged, and also allows you to look at the history of changes to the repo.

![image](https://user-images.githubusercontent.com/2446659/80924948-cda17780-8d51-11ea-834d-c1f43e95326a.png)

Currently, there isn't a lot of interesting history. Github did one commit for us when it created the README file for us. If we go back to the changes view, there's a useful button that can open up the file explorer to where it put our repository.

![image](https://user-images.githubusercontent.com/2446659/80925015-19ecb780-8d52-11ea-8062-9a0499ea3745.png)

If you don't have your file explorer configured to see hidden files, then you will probably just see the README.md file.

![image](https://user-images.githubusercontent.com/2446659/80925066-85368980-8d52-11ea-840b-9f5e4f825b02.png)

## Modify a file

Let's open up README.md in a text editor. Ideally, you should open it with a decent text editor (VS Code, Sublime Text, Notepad++, etc), but if you don't have one of those yet then you can use a terrible text editor like Notepad.

![image](https://user-images.githubusercontent.com/2446659/80925162-448b4000-8d53-11ea-9c7e-9ebd04987266.png)

![image](https://user-images.githubusercontent.com/2446659/80925094-bca53600-8d52-11ea-8911-00746a6aa608.png)

![image](https://user-images.githubusercontent.com/2446659/80925187-70a6c100-8d53-11ea-9312-634ed539558b.png)

Let's edit our file with our terrible text editor and add a happy message.

![image](https://user-images.githubusercontent.com/2446659/80925274-ff1b4280-8d53-11ea-9daf-c07611294b23.png)

Make sure you save the file.

Now if we look at the changes view in Github Desktop, it should tell us that one file has been modified and even show us what the modification was.

![image](https://user-images.githubusercontent.com/2446659/80925476-a9e03080-8d55-11ea-9b20-d55ebb73af07.png)

The right-side of the application is showing the file change as a "diff". The lines that start with a plus sign and are green are lines that have been added and lines that start with a minus sign and are red are lines that have been removed.

## Commit a change

On the bottom left side of Github Desktop is a place to commit your changes. Sometimes you need to stage files to indicate which changes you want to commit, but Github Desktop handles this for us, there's a checkbox next to each modified file for you to indicate which files you want to put in your commit. We need to add a commit message (although github desktop will write a default message for you if you don't).

![image](https://user-images.githubusercontent.com/2446659/80925550-4571a100-8d56-11ea-98a8-40b8ecd5f956.png)

Then we can click the commit to master button.

At this point we have created the commit and there shouldn't be any modified files anymore. If we look at the history view we can see that there should be two commits now.

![image](https://user-images.githubusercontent.com/2446659/80925636-10198300-8d57-11ea-898c-b4606f6194b0.png)

Committing our change does NOT send it to the server. The commit and the file changes only exist on our computer so far.

## Push

The button on the top left should no longer say fetch, now it should say Push. The 1 and the up arrow means that as far as your computer knows, there is one commit that is on your computer that is not on the github server. To send our commit up to the github server, we can push that button to send our commit up.

![image](https://user-images.githubusercontent.com/2446659/80925696-96ce6000-8d57-11ea-8f7e-546b17ce445f.png)

Now if we refresh the landing page of our repo, we should see that there are two commits and we can see our message is now in the README on the github server.

![image](https://user-images.githubusercontent.com/2446659/80925782-368bee00-8d58-11ea-905b-78f98bd942a7.png)

## Next Steps

* Install a decent text editor
* Create a new branch and try merging changes across branches.
* Try putting a non-text file into your repo like a PDF or a powerpoint document and see what happens.
