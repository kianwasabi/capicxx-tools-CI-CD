# Continuous Integration and Continuous Delivery for Convesa CommonAPI
Convesa offers a set of tools that can be used to generate CommonAPI code from FIDL (Interface Definition Language) and FDEPL (Deployment Descriptor) files. <br>
This GitHub Actions workflow automates the generation of CommonAPI code from FIDL  and FDEPL  files using the [CommonAPI Core](https://github.com/COVESA/capicxx-core-tools) and [CommonAPI vSOME/IP ](https://github.com/COVESA/capicxx-someip-tools) Generators. <br>
<br>
The workflow is triggered on push events to the "main" branch and when changes are made to FIDL and FDEPL files. <br>
It contains a single job called "commonapi-code-generator" that runs on ubuntu-latest. <br>
The job has six steps that checks out the repository, deletes old generated code, downloads the generators, generates CommonAPI code and saves the generated code to the main branch in a folder called "src-gen".

## How to use
Clone this repository to your local machine. <br>
```{bash}
git clone "https://github.com/kianwasabi/capicxx-tools-CI-CD.git"
cd fidl
```
Do your changes to the FIDL and FDEPL files. <br>
Push your changes to the "main" branch. <br>
```{bash}
git add .
git commit -m "updated my interface files - give me some code"
git push origin main
```
The workflow will be triggered and the generated code will be saved to the main branch in a folder called "src-gen". <br>
After this, pull the changes to your local repository. <br>
```{bash}
git pull origin main
```
The generated code is now ready to be used. <br>

## Note: 
- The [DBus Generator](https://github.com/COVESA/capicxx-dbus-tools) is not integreated in this automation.<br>
- There is also an official [workflow](https://github.com/COVESA/capicxx-someip-tools/tree/master/.github/workflows) that recently has been added to the convesa's repositories.

Feel free to use this workflow as a tool for your own projects. Maybe you want to add more steps to the workflow or use it with other generators. Or maybe the workflow is not suitable for your project and you want to create your own workflow from scratch. In any case, I hope this workflow will be useful to you. I assume the official workflow will be well maintained in the future and this workflow will be obsolete. :) <br>


