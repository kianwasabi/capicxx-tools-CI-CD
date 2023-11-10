# Continuous Integration and Continuous Delivery for Convesa CommonAPI
This GitHub Actions workflow automates the generation of CommonAPI code from FIDL (Interface Definition Language) and FDEPL (Deployment Descriptor) files using the CommonAPI Core and CommonAPI vSOME/IP or D-Bus Generators. 

## Intro
Convesa offers a set of tools that can be used to generate CommonAPI code from FIDL and FDEPL files. <br>
[DBus](https://github.com/COVESA/capicxx-dbus-tools) <br>
[Core](https://github.com/COVESA/capicxx-core-tools) <br>
[vSOME/IP](https://github.com/COVESA/capicxx-someip-tools) <br>
## Workflow
The workflow is triggered on push events to the "main" branch and when changes are made to FIDL and FDEPL files.
It contains a single job called "commonapi-code-generator" that runs on ubuntu-latest.
The job has six steps that: 
1) checkout the repository.
2) delete old generated code.
3) download the generators.
4) generate CommonAPI code.
5) save the generated code to the main branch in a folder called "src-gen".

## How to use

```{bash}
git clone "https://github.com/kianwasabi/capicxx-tools-CI-CD.git"
cd "this repository"
```

## Note: 
In Addition, there is also another [workflow] (https://github.com/COVESA/capicxx-someip-tools/tree/master/.github/workflows) that has been recently added to the convesa's repository. 
:)


