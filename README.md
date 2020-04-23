# Github Workflows for Azure Image Builder

Welcome to the Github workflows for Image Builder using ARM templates

## Purpose

The workflows (job) in this repo are created to create and run Azure Image Builder to customize the VM using Azure Resource Manager Templates. The ARM template examples in this repo also distribute the Azure VM images to the available distribution modes namely Azure Image Galleries (shared/private), Managed Images and VHDs.

## Documentation
There are multiple workflows in this repository under ./.github/workflows named with .yml as extension.  Each of the workflow takes the  the Azure Resource Manager template and parameter file and runs the Image Builder in an Azure resource group which is given in the inputs section under "with".

List of workflows available:
  1. *_mdi.yml for ubuntu custom image from platform image, distributed as Managed Images 
  2. *_sig.yml for ubnuntu custom image from Managed Image and distributed to shared image gallery
  3. *_sigmdi.yml for ubuntu custom image from Platform image, distributed as both managed image and to shared image gallery
  
## how to use it 
The workflows use standard ARM templates defined for various scenarios in https://github.com/lnochili/azvmimagebuilder/tree/master/armTemplates. 
  - Import the workflow file (e.g. aib_workflow_mdi.yml) into your repo under ./.githubrc/workflows
  - Update the triggers section to initiate the workflow as per your requiment
  - Import the respective parameters file (e.g. azplatform_image_params_mdi.json) from ./template_params directory into your repo
  - Update the parameters file with  all the values specific to your azure environment
  - Based on the trigger, the workflow is initiated and run to create the list of outputs : Managed Image, Shared Gallery Image, VHD
  
