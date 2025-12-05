ServiceNow CMDB CI Manual De-Duplication Task Creation Scheduled Job.

Steps: 
1.Modified the OOB Script Include CMDBDuplicateTaskUtils so that the short description of the De-Duplication task can be populated with a customised payload.

2. Created a Scheduled Job leveraging the script include to generate de-duplication tasks for pre-existing CIs on specific CMDB subclass tables based on a particular identifier. Here the class used in Linux Server and identifier is name.
var className = 'cmdb_ci_win_server';
var identifierAttr = 'name'
the classname and indentifierAttr can be changed based on the requirement.

3.Created a Scheduled Job leveraging the script include which will work on the main/master cmdb_ci table based on the identifier : name. On execution of the script de-duplication tasks will be generated where the short description will contain the name of the duplicate CI, the display and technnical name of the class and also the duplicate count

The Scheduled Job is runs on demand but you can make it work daily,weekly,periodically anytime.
