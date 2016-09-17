# CFN-VM-Imporit

## Summary:
This is an AWS cloudformation template to automate the creation and setup of the required IAM policies and roles to use the import export process.  It will also create the bucket which should be used to upload and import the virtual machine (VM) into AWS.  You can find detailed instructions to get this fully setup  here -> http://docs.aws.amazon.com/vm-import/latest/userguide/vmimport-image-import.html

## Outputs:
There will be 2 outputs.
- The name of the S3 bucket which should be used to upload and import your vm's
- An IAM group name which the user performing the import needs to be a member.  The group the user should be a member of is "ImportExportGroup".

## Known challenges
- This process requires a role with the specific name of "vmimport" if it is not named exactly the imports will fail.  This file does create this role with the correct name, but don't modify this role with something custom or it will cause failures.
- If there are are any existing roles or groups with the same name existing the template will fail. Please remove those groups if you feel comfortable and try again
- You will have to check some additional check boxes during the creation, its more for security awareness letting you know it's creating IAM resources.
