# Info on sia_repo_template
The purpose of this repo is to ensure that any IDI project that is started that depends on other repositories has all the necessary macros available (and the relevant versions of the macros). Dependence on other repositories is managed via submodules.

## Steps to creating a template for a project
1. `git clone --recursive https://nz-social-investment-agency/sia_repo_template.git`
2. Delete any folders you do not need (including submodule folders if they are not needed and the readmes in the subfolders that are just used as place holders) and update this readme.
3. Rename `sia_repo_template` to your project name
4. Zip up the folder
5. Email access2microdata@stats.govt.nz and ask them to drop the zipped file into your project area.


###Delete this line and everything above it ###


# <Main Title>

## Overview
<To be populated>

## Dependencies
* It is necessary to have an IDI Project if you wish to run the code. Visit the Stats NZ website for more information about this.
* Code dependencies are captured via submodules in Github. You will find the submodules in the `lib` folder of this repository. Currently the submodules available are the `social_investment_analytical_layer`, `social_investment_data_foundation`, `SIAtoolbox` and `mha_data_definition`. To ensure you clone the submodules as well use `git clone --recursive https://nz-social-investment-agency/sia_repo_template.git`, Regular cloning or downloading of the zip file will result in all the `lib` subfolders being empty.
* It is necessary to download and run the `social_investment_analytical_layer` scripts so that the SIAL tables exist for creating the service metrics (such as benefit costs, general medical subsidy costs and so on). We strongly recommend using the version in the submodule so that you always have access to the latest enhancements and bug fixes. Note when you create the SIAL tables, the script will attempt to access the following schemas in `IDI_Clean` (or the archives if you wish to use an older refresh):
    * acc_clean
    * cor_clean
    * cyf_clean
    * data
    * dia_clean
    * hnz_clean
    * moe_clean
    * moh_clean
    * moj_clean
    * msd_clean
    * pol_clean
    * security
* If there are specific schemas listed above that you don't have access to, the **SIAL** main script (after it finishes running) will give you a detailed report on which tables were not created and why.
* You can use the Data Foundation to roll up only those SIAL tables that were created. All these macros are made available via a `sasautos` call to the relevant `lib` subfolder. If you attempt to run the data foundation to create a variable from a SIAL table that does not exist in your schema the variables wont be created. You won't get an error, the variable just won't exist.

## Folder descriptions
<DELETE THE ONES YOU DONT NEED>
**docs:** This folder contains relevant documentation.
**examples:** This folder contains an example for training purposes.
**include:** This folder contains generic formatting scripts - gradually being deprecated.
**lib:** This folder is used to refer to reusable code that belongs to other repositories.
**logs:** This folder is used to store the output logs that SAS generates. This is used for the cross agency outcomes that have a lot of code to run.
**output:** This folder is used to store analytical output such as Excel tables and graphics.
**rprogs:** This folder contains R scripts (both a main script and functions).
**sasautos:** This folder contains SAS macros. All scripts here will be loaded into the SAS environment during the running of setup in the main script.
**sasprogs:**This folder contains SAS programs. The main script that builds the dataset is located in here as well as well as other SAS scripts that are not macros.
**unittests:** This folder contains unit tests for those who wish to debug the code.
* Note `sasprogs` is the only folder with scripts you need to edit to create a data foundation, unless you want to make changes to any source code.

## Installation
<To be populated>

## Instructions
<To be populated>

## Getting Help
If you have any questions email info@sia.govt.nz Tracking number: XXX-XXXX-XXXX
 

