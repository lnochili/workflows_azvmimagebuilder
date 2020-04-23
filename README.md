# Github Workflows for Azure Image Builder

Welcome to the Github workflows for Image Builder 

## Purpose

This workflow (job) is created to take your repo/build artifacts in github, and inject them into a VM image for Azure VM, customize the VM to install, configure your application, and OS.  The workflows also distribute the Azure VM images to the available distribution modes namely Azure Image Galleries (shared/private), Managed Images and VHDs.

## Documentation
There are multiple workflows in this repository under ./.github/workflows named with .yml as extension.  Each of the workflow takes the  the Azure Resource Manager template and parameter file and runs the Image Builder in an Azure resource group which is given in the inputs section under "with".
List of workflows available:
  1. *_mdi.yml for ubuntu custom image from platform image, distributed as Managed Images 
  2. *_sig.yml for ubnuntu custom image from Managed Image and distributed to shared image gallery
  3. *_sigmdi.yml for ubuntu custom image from Platform image, distributed as both managed image and to shared image gallery


End to End Example (with video guide!!)
Step by step guide on how to create a custom image build pipeline, where you can bake your apps into an image, configure the OS, and then distribute globally.
workflows for azure vm image builder using ARM templates 

1. *_mdi.yml for ubuntu custom image from platform image distributed as Managed Images 
2. *_sig.yml for ubnuntu custom image from Shared image gallery and distributed to shared image gallry
