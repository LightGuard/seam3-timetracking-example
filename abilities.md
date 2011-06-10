This document lists the abilities of the application, both at a high level and
also more fine grained. The abilities are also backed by some examples to help
drive development.

## User has ability to login / logout
1. The user should be able to login with a username and password.
  * User supplies the correct cedentials
  * The site attempts to authenticate the credentials and redirects to the logged time view


  * User supplies incorrect credentials
  * The site attempts to authenticate the credentials and displays an error message stating the problem

2. The user will be automatically logged out after a time of inactivity
  * No actions happen from the user for a period of time
  * Upon the next interaction with the application the user is directed to login again due to inactivity

3. The user should be able to manually log out of the application
  * When a user manually logs out of the application they are redirected back to the main landing page of the site

## User has ability to add / edit / delete / view projects
A project contains a name, and a starting date and an ending date

  * When a user enters the project section of the site they can enter the above date for a new project
  * When a user is in the project section they are presented with a list of projects with their names and dates
  * Upon selecting a project they can delete that project or edit any of the above mentioned properties

  At the time of adding a new project or editing the properties of an existing project the dates are validated

  * The starting date must be equal to or greater than the current date
  * The ending date must be after the starting date


    The following data is input:
       * Start date: June 1st, 2011 (the current date is June 3rd, 2011)
       * End date: May 30th, 2011
       * Name: Acme Co.
    The system will alert the user that the start date occurs before the current date and the end date must be
    after the starting date.

    The following data is input:
       * Start date: 06/15/2011 (the current date is June 3rd, 2011)
       * End date: 2011/06/06
       * Name: Acme Co.
    The system will alert the user the ending date is before the starting date

    The following data is input:
       * Start date: 06-07-2011 (the current date is June 3rd, 2011)
       * End date: 07-01-2011
       * Name: Acme Co.
    The system accepts the date and creates a new project.

    The following data is edited
      * Start date: blah blah .34 #$%*
      * End date: 07-01-2011 (not changed)
      * Name: Acme Co. (not changed)
    The system alerts the user to invalid date entered for the start date

    The following data is input:
      * Start date:
      * End date:
      * Name:
    The sytem will alert the user to the missing name and start date.

## User has ability to log / edit time against a project
Time should be logged in hours (fractional hours such as 1.5 or 1.25 are permissable)
and be associated with a date and project.

    The following data is entered:
      * Hours: -1
      * Date: 2011-06-24
      * Project: Acme Co
    The application will alert the user to an invalid entry of negative hours

    The following data is entered:
      * Hours: abc
      * Date: 2011-06-24
      * Project: Acme Co
    The application will alert the user to an invalid entry of negative hours

    The following data is entered:
      * Hours: 1
      * Date: 2011-06-24
      * Project: Acme Co
    The application add the hours to the selected project

    The following data is entered:
      * Hour: 2.5
      * Date: &$a4-23-1
      * Project: Acme Co
    The application will alert the user to an invalid date entry

    The following data is entered:
      * Hour: 3
      * Date: 2011-06-24
      * Project: Invalid Project (this project is not in the system)
    The application will alert the user about an invalid project selection

## User has ability to export time into a report
The user should be able to export a view of logged time as (at least) a PDF report.
A view could be of a month, a week or a project.

## User has ability to view logged time
Logged time should be viewable as a monthly calendar, weekly calendar or as a list
for a whole project.
