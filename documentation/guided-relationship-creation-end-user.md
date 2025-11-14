## **SOP: Guided Relationship Creation Screenflow**

### **Objective**

This screenflow was developed to address Education Cloud’s lack of an automated reciprocal relationships in Contact Contact Relationships, the lack of sync in Contact Contact and Account Contact Relationships, and because out-of-the-box Account Contact Relationships do not have individual start/end dates for a person’s many relationships to the same object. That is, a Person Account (Contact) can be related to an Account (a single Account Contact Relationship record) with a single start date and a single end date. The record does have a multi-select picklist for Role so the Contact can have many roles (e.g., current graduate student, alumnus, and parent). The problem, however, is that roles need to have their own start-and-end date. 

So, this solution introduces a custom object (Contact Account Relationships) that users engage with while at the same time, creating records in the native Account Contact Relationship in the background. That background work was included in an abundance of caution, mostly because AI native to Salesforce will expect the records to be available natively, and we didn’t want to preclude AI’s use of them just because we introduced a custom object. 

This document provides a clear, step-by-step guide for team members to effectively create and manage relationships between person accounts and organization accounts using the Guided Relationship Creation Screenflow. This SOP aims to minimize misunderstandings and errors while maximizing productivity and accuracy in task execution.

### **Key Steps**

1. **Access the Guided Relationship Creation Screenflow**  
   * Open the application and navigate to the Guided Relationship Creation Screenflow.  
2. **Creating a Person-to-Person Relationship**  
   * Select the option for "Person-to-Person Relationship."  
   * Confirm that the person account (e.g., Thomas Drill-Trail Blazer) is pre-filled on the left.  
   * Enter the related contact’s name (e.g., Jane Masterson).  
   * Select the relationship type:  
     * Advisor-to-Advisor (ensure you select the correct direction).  
   * Verify that the description indicates the correct relationship (e.g., Thomas Trailblazer is Jane Masterson's advisee).  
   * Set the start date for the relationship.  
   * Click "Next" to confirm the relationship creation.  
   * Look for a success message indicating the relationship has been created.  
3. **Creating a Contact-Contact Relationship**  
   * Navigate to the contact-contact relationships section to confirm the relationship is displayed.  
   * Note that an inverse record will be automatically created for the related contact.  
4. **Creating a Person-to-Organization Relationship**  
   * Select the option for "Person-to-Organization Relationship."  
   * Confirm that the person account (e.g., Thomas Trailblazer) is pre-filled.  
   * Select the organization (e.g., Salesforce).  
   * Specify the role (e.g., Thomas Trailblazer as an intern).  
   * Set the start date for the relationship.  
   * Click "Next" to confirm the relationship creation.  
   * Verify that the relationship appears under contact-account relationships.  
5. **Creating an Organization-to-Person Relationship**  
   * Select the option for "Organization-to-Person Relationship."  
   * Confirm that the organization (e.g., Connected University) is pre-filled.  
   * Enter the contact’s name (e.g., Jane Masterson).  
   * Confirm the relationship is displayed under contact-account relationships.  
6. **Creating an Organization-to-Organization Relationship**  
   * Select the option for "Organization-to-Organization Relationship."  
   * Confirm that the organization (e.g., Connected University) is pre-filled.  
   * Select the related organization (e.g., Salesforce).  
   * Specify the relationship details (e.g., Connected University as the internship organizer).  
   * Set the start date for the relationship.  
   * Click "Next" to confirm the relationship creation.  
   * Verify that the account-account relationship is displayed and note the automatic creation of the inverse record.

### **Cautionary Notes**

* Ensure that the correct relationship type is selected to avoid confusion in the relationship direction.  
* Double-check all pre-filled information to confirm accuracy before proceeding.  
* Be aware of the automatic inverse records created for contact-contact and account-account relationships. (Well, that’s really one of the points of this, anyway.)

### **Tips for Efficiency**

* Familiarize yourself with the relationship types and their implications to speed up the selection process.  
* Regularly review and update relationships as needed to ensure they reflect current statuses.

### **Link to Video**

[https://loom.com/share/308a396772a848c6918bfd345d687a39?src=composer](https://loom.com/share/308a396772a848c6918bfd345d687a39?src=composer)

## **Step by Step: Understanding the Guided Relationship Creation Screenflow**

### **1\. Overview of the Screenflow**

* Purpose: Review the Guided Relationship Creation Screenflow for person accounts and regular accounts.

### **2\. Creating Person-to-Person Relationships**

* **Step 1:** Select person-to-person relationship option.  
* **Step 2:** Confirm pre-filled Person Account (e.g., Thomas Trailblazer).  
* **Step 3:** Enter related contact (e.g., Jane Masterson).  
* **Step 4:** Choose the relationship type:  
  * Advisee-to-advisor (Thomas as advisor to Jane).  
* **Step 5:** Confirm relationship description.  
* **Step 6:** Set start date and proceed.  
* **Outcome:** Success message and display of contact-contact relationship.

### **3\. Creating Person-to-Organization Relationships from Person Accounts**

* **Step 1:** Select person-to-organization relationship option.  
* **Step 2:** Confirm pre-filled contact (e.g., Thomas Trailblazer).  
* **Step 3:** Select related organization (e.g., Salesforce).  
* **Step 4:** Define role (e.g., Thomas as intern).  
* **Step 5:** Set start date and proceed.  
* **Outcome:** Display of contact-account relationship with active status.

### **4\. Creating Person-to-Organization Relationships from Accounts**

* **Step 1:** Select organization-to-person relationship option.  
* **Step 2:** Confirm pre-filled account (e.g., Connected University).  
* **Step 3:** Enter related contact (e.g., Jane as an employee).  
* **Outcome:** Display of contact-account relationship.

### **5\. Creating Organization-to-Organization Relationships**

* **Step 1:** Select organization-to-organization relationship option.  
* **Step 2:** Confirm pre-filled account (e.g., Connected University).  
* **Step 3:** Select related organization (e.g., Salesforce).  
* **Step 4:** Define roles (e.g., Connected University as internship organizer).  
* **Step 5:** Set start date and proceed.  
* **Outcome:** Creation of account-account relationship with inverse record.

### **6\. Conclusion**

* Summary of the relationship creation process and the automatic generation of inverse records for both contact and account relationships.

### **Link to Video**

[https://loom.com/share/308a396772a848c6918bfd345d687a39?src=composer](https://loom.com/share/308a396772a848c6918bfd345d687a39?src=composer)

## **QA Steps: Steps to Reproduce the Bug in Guided Relationship Creation Screenflow**

### **Environment**

* **OS:** Not specified  
* **Browser:** Not specified  
* **Device:** Not specified

### **Steps**

1. **Access Person Account:**  
   * Navigate to a Person Account (e.g., Thomas Trailblazer).  
2. **Create Person-to-Person Relationship:**  
   * Select "Create a person-to-person relationship."  
   * Confirm that Thomas Trailblazer is pre-filled on the left side.  
   * Enter a related contact name (e.g., Jane Masterson).  
   * Choose the relationship type (e.g., "advisee-to-advisor").  
   * Verify the description that appears, confirming the relationship (e.g., "Thomas Trailblazer is Jane Masterson's advisee").  
   * Set the start date and click "Next."  
   * Confirm the success message appears.  
3. **Verify Contact-Contact Relationship:**  
   * Check the Contact-Contact Relationships related list to confirm that the relationship was created.  
   * Click into the relationship to view the automatically created inverse record.  
4. **Create Person-to-Organization Relationship:**  
   * Select "Create a person-to-organization relationship."  
   * Confirm that the contact (Thomas Trailblazer) is pre-filled.  
   * Select the organization (e.g., Salesforce).  
   * Assign a role (e.g., "intern") and set the start date.  
   * Click "Next" and verify that the Contact-Account Relationship is created with Active status.  
5. **Access Regular Account:**  
   * Navigate to a regular account (e.g., Connected University).  
6. **Create Organization-to-Person Relationship:**  
   * Select "Create an organization-to-person relationship."  
   * Confirm that the account is pre-filled.  
   * Enter the contact name (e.g., Jane Masterson) as an employee.  
   * Verify the Contact Account Relationship is created.  
7. **Create Organization-to-Organization Relationship:**  
   * Select "Create an organization-to-organization relationship."  
   * Confirm that Connected University is pre-filled.  
   * Select another organization (e.g., Salesforce) and define the relationship (e.g., "Connected University is the internship organizer").  
   * Set the start date and click "Next."  
   * Verify that the Account Account Relationship is created, including the inverse record.

### **Note**

* Ensure that all relationships created reflect correctly in both directions (inverse records).

### **Link to Video**

[https://loom.com/share/308a396772a848c6918bfd345d687a39?src=composer](https://loom.com/share/308a396772a848c6918bfd345d687a39?src=composer)

## **Code Docs: Guided Relationship Creation Screenflow Documentation**

This document outlines the functionality of the Guided Relationship Creation Screenflow component, which supports both person accounts and regular accounts.

### **Overview**

The Guided Relationship Creation Screenflow allows users to create various types of relationships between accounts and contacts. The component supports the following relationship types:

* Person-to-Person  
* Person-to-Organization  
* Organization-to-Person  
* Organization-to-Organization

### **Person Account Relationships**

#### **Person-to-Person Relationship (Contact Contact Relationships)**

1. **Selection**: Choose the option to create a person-to-person relationship.  
2. **Pre-filled Data**: The currently viewed person account (e.g., Thomas Trailblazer) is pre-filled on the left.  
3. **Related Contact**: Enter the name of the related contact (e.g., Jane Masterson).  
4. **Relationship Type**: Select the relationship type (e.g., Advisee-to-Advisor).  
   * Example: Thomas Trailblazer is Jane Masterson's advisee.  
5. **Start Date**: Set the start date for the relationship.  
6. **Success Message**: Upon completion, a success message is displayed.  
7. **Contact-Contact Relationships**: The relationship will be visible under the Contact Contact Relationships related list, including an automatically created inverse record.

#### **Person-to-Organization Relationship (Contact Account Relationships from Person Account)**

1. **Selection**: Choose the option to create a person-to-organization relationship.  
2. **Pre-filled Data**: The contact (e.g., Thomas Trailblazer) is pre-filled.  
3. **Account Selection**: Select the organization (e.g., Salesforce).  
4. **Role**: Assign a role (e.g., Intern).  
5. **Start Date**: Set the start date for the relationship.  
6. **Active Status**: The relationship will be displayed under Contact Account Relationships with an Active status set to true.

### **Regular Account Relationships (Contact Account Relationships from an Account that is not a Person Account)**

#### **Organization-to-Person Relationship**

1. **Selection**: Choose the option to create an organization-to-person relationship.  
2. **Pre-filled Data**: The current organization (e.g., Connected University) is pre-filled.  
3. **Related Contact**: Enter the name of the contact (e.g., Jane Masterson).  
4. **Contact-Account Relationships**: The relationship will be visible under Contact Account Relationships.

#### **Organization-to-Organization Relationship**

1. **Selection**: Choose the option to create an organization-to-organization relationship.  
2. **Pre-filled Data**: The current organization (e.g., Connected University) is pre-filled.  
3. **Related Organization**: Select the related organization (e.g., Salesforce).  
4. **Role**: Assign a role (e.g., Internship Organizer).  
5. **Start Date**: Set the start date for the relationship.  
6. **Account-Account Relationships**: The relationship will be visible under Account Account Relationships, including an automatically created inverse record.

### **Conclusion**

This Guided Relationship Creation Screenflow provides a streamlined process for establishing various types of relationships between person accounts and organizations, ensuring that all relevant data is captured and displayed appropriately, stays in sync, and has individual start and end dates..

### **Link to Video**

[https://loom.com/share/308a396772a848c6918bfd345d687a39?src=composer](https://loom.com/share/308a396772a848c6918bfd345d687a39?src=composer)

