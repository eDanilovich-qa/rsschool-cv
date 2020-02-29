# CV - Yauheni Danilovich

## Personal Info

First Name: **Yauheni**

Last Name: **Danilovich**

Contact Info: **bluerayend@gmail.com**

## Summary 

QA Automation Engineer wants to become a developer

## Skills

**Programming languages:**

* c#
* python
* groovy
 
**Frameworks:**

* specflow
* selenium
* robot framework

**Version control:**

* gitlab
* bitbucket

**Other tools:**

* linux, ubuntu
* atlassian (jira, bitbucket, and so on)
* .NET MVC
* windows os
* CIs (jenkins, teamcity, bamboo)
* teststack.white
* knowledges at design patterns

## Code examples (LATEST)

```
BDD Testing using specflow, gerkin:

@Client-Server @Workstation @LDAP @LocalUser
Feature: Privileges_Management_32_DeleteECordColumns

Background: 
	Given These Users exist with following User Types and have all privileges except Administrator and the ones below: 
		| Username                 | User type             | Excluded Privilege    |
		| NoAlterSPUser            | NoAlterSystemPolicies | Alter System Policies |
		| NoDeleteEcordColumnsUser | NoDeleteEcordColumns  | Delete eCord Columns  |
		And Ecord column data were restored from 'ecord_data.dmp' file via database

Scenario Outline: Privileges_Management_32.1 - Delete eCord Columns
	Given User is logged in Configuration Manager as '<User>' having default password
		And The 'eCord' tree node has been opened in Configuration Manager
	When I select the '1' table row in Configuration Manager
	Then @The 'Edit\Delete' menu item is '<Delete_Option_State>' in 'Configuration Manager' window
	When I open context menu for selected rows in the Configuration Manager table
	Then @The 'Delete' item is '<Delete_Option_State>' in context menu
	When I select the '1' table row in Configuration Manager
		And I press 'DELETE' key
	Then <EventOnDelKey>
Examples: 
	| User                     | Delete_Option_State | EventOnDelKey                             |
	| NoDeleteEcordColumnsUser | disabled            | No popups are displayed                   |
	| NoAlterSPUser            | enabled             | The 'Delete Confirmation' popup is opened |

BL logic:

public void CreateUserWithUserType(List<UserDTO> users)
        {
            foreach (var user in users)
            {
                TKUserType.CreateUserTypeWithoutPrivileges(user.UserType, PrivilegeTypeConverter.GetPrivilegesList(user.ExcludedPrivilege));
                if (!TKUser.CheckUserWithUserTypeExists(user.UserName, user.UserType))
                {
                    TKUser.CreateUser(user.UserName, user.UserType, ConfigReader.DefaultTestUserPassword, user.PasswordRequired);
                }
                UsersBL.LinkUserWithDomainIfLDAPOn(user.UserName, ConfigReader.DefaultLDAPUser);
            }
        }
```

## Experience

2.5 years in QA Automation testing.

**Responsibilities:**

* developinng test framework
* writing tests
* analysing test results
* communication with customer
* existing test support
* setting up CI

## Education

Graduated from Belarusian National Technical University in 2018

## English: 

English level: **Intermediate (B1)**

**Experience:**

* 3 months of business trip in Romania (communication with customer in English)
* participated in 2 English-language projects
* 4 english courses completed (Business english, Communicative grammar, Spoken and so on)
