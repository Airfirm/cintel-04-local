# PyShiny Express: Palmer Penguins Dashboard

### Verify App Runs
- Run shiny app. -shiny run --reload --launch-browser penguins/app.py
### Build Client-Side App
- We will build the app to the docs folder of our repository and test it locally. Run-shiny static-assets remove \n shinylive export penguins docs
- After the app is built, serve the app locally from the docs folder to test before publishing to GitHub Pages.
- In the terminal, run the following command from the root of the project folder with the project virtual environment active:
- Run-py -m http.server --directory docs --bind localhost 8008
### Git Add / Commit / Push to GitHub
- git add .
- git commit -m "commit message"
- git push -u origin main
### Publish GitHub pages for the Repo
"""
This is a one-time step. We need to set up your GitHub repo (in the cloud) so that it will host with GitHub Pages. 

The first time you set up an app to use Pages, navigate to the repository on GitHub and configure the settings to publish the app with GitHub Pages.
After configuring the repository once, each time you push changes to the main branch, the app will automatically update.

Go to the repository on GitHub and navigate to the **Settings** tab.
Scroll down and click the **Pages** section down the left.
Select branch main as the source for the site.
Change from the root folder to the docs folder to publish from.
Click Save and wait for the site to build.
Eventually, be patient, your app will be published and if you scroll to the top of the Pages tab, you'll see your github.io URL for the hosted web app. Copy this to your clipboard. 
Back on the main repo page, find the About section of the repo (kind of upper right).
Edit the "About" section of the repository to include a link to your hosted web app by using the Pages URL. 
When Finished

When you finish, you should have a working, unique version of a penguin dashboard that you can work with locally on your machine and have published for free on the web. It should have several inputs including a drop down to select a column for display that works and a checkbox group for species that is used to reactively filter the species shown on the charts. It should use a reactive calc to filter the dataframe and use the filtered dataframe for your tables, grids, and charts. 

https://airfirm.github.io/cintel-04-local/
"""
### Change the Browser Tab Title
"""
Back on your machine, in VS Code, open the new docs folder. Edit docs/index.html - find the line that has the <title> and </title> opening and closing tags. The inner text between these two tags will appear in your tab. It's currently the same for everyone. Make this unique. 

Replace the title with your own short custom title - it will display in the browser tab when your app runs. 
"""
### Optional - Add a Custom Favicon
"""
Optional: Add your own custom favicon  (the little icon that appears in the web browser tab) next to the title. Try https://favicon.io/Links to an external site. and create a favicon (the little icon that appears in the web browser tab) using a bit of text (e.g. PP for popper's penguins  - or better yet, your own unique icon). Download the zip file and extract the files. Take just the favicon.ico file and paste it into your docs folder.  Two changes are required:

Confirm there is a favicon.ico in your docs folder. 
Edit docs/index.html -  Just below the title line, add the following link tag like so. This code is the same for all of us - only the favicon appearance is different. If your favicon.ico has a different name or path, let VS Code help you provide the correct path. 
- Run  <title>PyShiny Penguins</title>
-      <link rel="icon" type="image/x-icon" href="./favicon.ico">
"""

- Repository: [pyshiny-penguins-dashboard-express](https://github.com/denisecase/pyshiny-penguins-dashboard-express)
- Live App: [Penguins Dashboard (Express)](https://denisecase.github.io/pyshiny-penguins-dashboard-express/)

Run and publish interactive apps using PyShiny Express and GitHub Pages.

This is a teaching version of the app written for clarity and understanding.
To contribute, please fork the repository and submit a pull request.

## Data Description

This app uses the Palmer Penguins dataset which includes three penguin species observed on three islands in the Palmer Archipelago, Antarctica.
The data has been made available by Dr. Kristen Gorman and the Palmer Station, Antarctica LTER, a member of the Long Term Ecological Research Network.

Column names for the penguins dataset include:

- species: penguin species (Chinstrap, Adelie, or Gentoo)
- island: island name (Dream, Torgersen, or Biscoe) in the Palmer Archipelago
- bill_length_mm: length of the bill in millimeters
- bill_depth_mm: depth of the bill in millimeters
- flipper_length_mm: length of the flipper in millimeters
- body_mass_g: body mass in grams
- sex: MALE or FEMALE

See: <https://allisonhorst.github.io/palmerpenguins/>

## Data Cleaning and Transformation

The data includes some missing values.
We generally clean the data by removing rows with missing values and possibly transform the data to use columns that are more easily read (or use labels on charts and tables).

## Source

From <https://shiny.posit.co/py/docs/user-interfaces.html>.
This version has been modified slightly for hosting with GitHub Pages.

## Prerequisites

Before you start, have the following installed:

- **Python**: Install the most recent version from [python.org](https://www.python.org/downloads/).
- **Git**: Download and install Git from [git-scm.com](https://git-scm.com/downloads).
- **Visual Studio Code (VS Code)**: Download from [code.visualstudio.com](https://code.visualstudio.com/).
- **VS Code Extensions**: Install the Python extension and the Shiny extension in VS Code.

### Configurations

- **Configure Git**: Set up your user name and email with Git using the following commands in your terminal.
Change the values to your name and email address. This is a one-time setup.

  ```shell
  git config --global user.name "Your Name"
  git config --global user.email "youremail@example.com"
  ```

## Set up the Project

### Commands

Commands are operating system-specific.
These commands are for Windows users.
On Mac/Linux, generally use `python3` instead of `py`.
Edit your README.md to reflect the commands that work on your machine.

### Verify Installations

1. Open project folder in VS Code.
2. Open a new terminal - on Windows, ensure the terminal type is PowerShell (not the old cmd)
3. Run the following commands in the terminal one at a time to verify installations.

```shell
py --version
git --version
git config user.name
git config user.email
```

## Python Project Virtual Environment

Run the following commands in the terminal to set up a project virtual environment and install the necessary packages.
Run them from the root project folder (e.g. pyshiny-penguins-dashboard-express).
Use PowerShell on Windows or the terminal on macOS and Linux.

### Create a Project Virtual Environment (generally one-time setup)

Create a project virtual environment in the .venv folder of the project root directory.

  ```shell
  py -m venv .venv
  ```

Creating a project virtual environment is generally a one-time setup.
Once the folder exists, we can activate it to work on the project.

If VS Code pops up and says: We noticed a new environment has been created.
Do you want to select it for the workspace folder? select Yes.

### Activate the Project Virtual Environment (when you work on the project)

Once the project virtual environment exists,
 we activate the virtual environment to work on the project - or when we open a new terminal.

On Windows:

  ```shell
  .venv\Scripts\Activate
  ```

On macOS and Linux:

  ```shell
  source .venv/bin/activate
  ```

Verify: Generally when the environment is active, (.venv) will appear in the terminal prompt.

We also need to select this project virtual environment in VS Code. To do this:

1. Open the VS Code command palette (Ctrl+Shift+P).
2. Search for "Python: Select Interpreter".
3. Select the .venv folder in the project root directory.

### Install Packages into the Active Project Virtual Environment

When the project virtual environment is active,
install packages into the project virtual environment so they are available for use in the Python code.

NOTE:

- We **install** packages into the project virtual environment.
- We **import** packages into Python code (after they have been installed).

First, upgrade pip and setuptools (core packages) for good measure.
NOTE: Using the palmerpenguins package requires setuptools.
Then, install the project-specific required packages.

With the project virtual environment **active** in the terminal, run the following commands:

```shell
py -m pip install --upgrade pip setuptools
py -m pip install --upgrade -r requirements.txt
```

Installing packages is generally a one-time setup.

## Run the App

With your project virtual environment **active** in the terminal
 and the necessary packages installed, run the app with live reloading and
 automatically open it in the browser:

```shell  
shiny run --reload --launch-browser penguins/app.py
```

While the app is running, that terminal is fully occupied.
Open a new terminal to run other commands.

## Build the App to Docs Folder and Test Locally

With your project virtual environment **active** in the terminal
 and the necessary packages installed, remove any existing assets and use
 shinylive export to build the app in the penguins folder to the docs folder:

```shell
shiny static-assets remove
shinylive export penguins docs
```

**Optional:** Edit docs/index.html to show a custom tab title and add a favicon.

This optional effort changes the HTML so the GitHub Pages web app will open in a tab with a custom title and favicon image. 
For it to work, you'll need to first build your own favicon at https://favicon.io/.
Open <https://favicon.io/>.
Design an icon, e.g. using text & your initials. Set the colors and font. 
Save the file as a zip file and extract (unzip) all the files somewhere on your machine.
Copy the file named **favicon.ico** file to your project **docs** folder so your html file can find it.  

```html
    <title>PyShiny Penguins</title>
    <link rel="icon" type="image/x-icon" href="./favicon.ico">
```

After the app is built, serve the app locally from the docs folder to test before publishing to GitHub Pages.
In the terminal, run the following command from the root of the project folder:

```shell
py -m http.server --directory docs --bind localhost 8008
```

Open a browser (tested with Chrome) and navigate to [http://localhost:8008](http://localhost:8008) to view the app running locally.

## After Editing, Git Add/Commit/Push Changes to GitHub

After editing project files, use Git add/commit/push changes to the main branch of the repository.
Note that if a terminal is serving an app, it is not available for other commands.
Run the following commands from a new or available terminal to git add/commit/push changes to GitHub.
Replace "Your commit message" with a meaningful message about the changes you made to the project files.
Run commands one at a time and wait for each to complete before running the next.

```shell
git add .
git commit -m "Your commit message"
git push -u origin main
```

## Publish the App with GitHub Pages (one-time setup)

The first time you set up an app, you'll need to navigate to the repository on GitHub and configure the settings to publish the app with GitHub Pages.
After configuring the repository once, each time you push changes to the main branch, the app will automatically update.

1. Go to the repository on GitHub and navigate to the **Settings** tab.
2. Scroll down and click the **Pages** section.
3. Select branch **main** as the source for the site.
4. Change from the root folder to the **docs** folder to publish from.
5. Click Save and wait for the site to build.
6. Edit the "About" section of the repository to include a link to the live app.

## Resources

Example csv data from [penguins.csv](https://github.com/mwaskom/seaborn-data/blob/master/penguins.csv).
Used for review only. In the app, we import the data from the palmerpenguins package.

Palmer Penguins published in:

- Horst AM, Hill AP, Gorman KB (2020). palmerpenguins: Palmer
Archipelago (Antarctica) penguin data. R package version 0.1.0.
 <https://allisonhorst.github.io/palmerpenguins/>. doi:
10.5281/zenodo.3960218.

Data originally published in:

- Gorman KB, Williams TD, Fraser WR (2014). Ecological sexual dimorphism and environmental variability within a community of Antarctic penguins (genus Pygoscelis). PLoS ONE 9(3):e90081. <https://doi.org/10.1371/journal.pone.0090081>

The Shiny development team. Shiny for Python [Computer software]. <https://github.com/posit-dev/py-shiny>

## Screenshots

Running the Shiny for Python app locally on port 8000.

![Running the Shiny for Python app locally](./images/LocalAppRunning.JPG)

Serving the static app locally from the **docs** folder (as GitHub Pages will) on port 8008.
The browser tab shows a custom tab title and favicon.
Recommended: Build your own favicon at <https://favicon.io/>.

![Serving the app locally from the docs folder](./images/ServingAppLocally.JPG)