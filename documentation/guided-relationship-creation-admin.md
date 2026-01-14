## **SOP: Automation and Screen Flow for Relationship Objects in Education Cloud**

### **Objective**

This screenflow was developed to address Education Cloud’s lack of automated reciprocal relationships in Contact Contact Relationships, the lack of sync in Contact Contact and Account Contact Relationships, and because out-of-the-box Account Contact Relationships do not have individual start/end dates for a person’s many relationships to the same object. That is, a Person Account (Contact) can be related to an Account (a single Account Contact Relationship record) with a single start date and a single end date. The record does have a multi-select picklist for Role so the Contact can have many roles (e.g., current graduate student, alumnus, and parent). The problem, however, is that roles need to have their own start-and-end date. 

So, this solution introduces a custom object (Contact Account Relationships) that users engage with while at the same time, creating records in the native Account Contact Relationship in the background. That background work was included in an abundance of caution, mostly because AI native to Salesforce will expect the records to be available natively, and we didn’t want to preclude AI’s use of them just because we introduced a custom object. 

This document provides a clear and comprehensive step-by-step guide for admins to effectively understand the automation and screen flows. This SOP aims to minimize misunderstandings and errors while maximizing productivity and accuracy in task execution.

### **Key Steps**

1. **Identify the Context of Record Creation**  
   * Determine whether you are working with a Person Account or an Organization Account.  
   * Decide the type of relationship to create:  
     * Person to Person  
     * Person to Organization  
     * Organization to Person  
     * Organization to Organization  
2. **Creating Records via Guided Screen Flow**  
   * **For Person to Person:**  
     * Pre-fill the contact name from the account.  
     * Enter the related contact’s name and relationship type.  
     * Check for existing active relationships. If one exists, display an error message.  
   * **For Person to Organization:**  
     * Pre-fill the contact name from the account.  
     * Enter the account name, start and end dates, and relationship type.  
     * Check for existing active relationships and create the necessary records.  
   * **For Organization to Organization:**  
     * Enter the required details and check for existing active relationships.  
     * Create the account account relationship record if no duplicates exist.  
3. **Automation Flows**  
   * Implement three main automation flows for each relationship type:  
     * **Before Save Flow:** Set the active checkbox based on start and end dates.  
     * **After Save Flow:** Create and synchronize reciprocal relationships.  
     * **On Delete Flow:** Remove orphaned relationships when a record is deleted.  
4. **Custom Object Handling (Contact Account Relationship)**  
   * Set a duplicate key to prevent duplicate records.  
   * Implement specific flows for creating and updating records based on the relationship type (e.g., Household Member or Employee).  
   * Ensure that changes to active status are reflected in related records.  
5. **Final Checks and Validation**  
   * Confirm that all relationships are accurately recorded and that there are no orphaned records.  
   * Ensure that any changes made to records are reflected in the corresponding reciprocal relationships.

### **Cautionary Notes**

* Ensure that no two active relationships of the same type exist between the same individuals.  
* Be cautious when updating or deleting records to prevent unintended orphaned relationships.  
* Always double-check for existing relationships before creating new ones to avoid duplicates.

### **Tips for Efficiency**

* Utilize pre-filled fields to minimize data entry errors.  
* Regularly audit existing relationships to ensure data integrity.  
* Familiarize yourself with the automation flows to better understand how changes will affect related records.  
* Keep documentation updated to reflect any changes in the process or system updates to the Education Cloud.

By following these steps, team members can effectively manage relationship records within the Education Cloud, ensuring accuracy and efficiency in their tasks.

### **Link to Video**

[https://loom.com/share/eb7eda81fcd241128f6e383773817a9b?src=composer](https://loom.com/share/eb7eda81fcd241128f6e383773817a9b?src=composer)

## 

## **Step By Step: Understanding Automation and Screen Flow for Relationship Objects in Education Cloud**

### **1\. Introduction**

* Overview of the video’s purpose: reviewing automation and screen flow for relationship objects in Education Cloud.  
* Emphasis on maintaining relationship records.

### **2\. Guided Screen Flow for Record Creation**

* **Purpose of the Flow**:  
  * Designed for use on person accounts or organization accounts.  
  * Allows creation of various relationship types:  
    * Person to Person  
    * Person to Organization  
    * Organization to Person  
    * Organization to Organization  
* **Main Objects Involved**:  
  * Standard Objects:  
    * Account  
    * Account Relationship  
    * Contact  
    * Contact Relationship  
    * Account Contact Relationship  
  * Custom Object:  
    * Contact Account Relationship (to track unique relationships)

### **3\. Flow Paths**

* **Person to Person**:  
  * Pre-fills contact name.  
  * User inputs related contact and relationship type.  
  * Checks for existing active relationships to prevent duplicates.  
* **Person to Organization**:  
  * Creates Contact Account Relationship record.  
  * Similar process as Person to Person but focuses on organization details.  
* **Organization to Organization**:  
  * Creates Account Account Relationship record.  
  * Follows a similar path as Person to Person.

### **4\. Automation Processes**

* **Contact Contact Relationship (CCR) Automation**:  
  * **Before Save**: Updates the active checkbox based on the relationship's start and end dates.  
  * **After Save**: Creates/syncs reciprocal relationships automatically.  
  * **On Delete**: Deletes reciprocal relationships to avoid orphaned records.  
* **Account Account Relationship (AAR) Automation**:  
  * Identical processes as CCR automation.  
* **Contact Account Relationship (CAR) Automation**:  
  * **Before Save**: Updates active checkbox and prevents duplicates.  
  * **After Save**: Syncs related records and creates employment links.  
  * **On Delete**: Similar to CCR, checks and updates related records.

### **5\. Detailed Automation Logic for CAR**

* **Before Save**:  
  * Sets criteria for active status and duplicate prevention.  
* **After Save**:  
  * Links household accounts and creates person employment records based on relationship type.  
  * Updates existing records if the relationship changes or becomes inactive.  
* **On Delete**:  
  * Ensures removal of roles from ACR or deletion of ACR if it's a one-to-one relationship.

### **6\. Conclusion**

* Summary of the automation and flow processes designed to manage relationship records effectively within Education Cloud.  
* Emphasis on the importance of maintaining accurate and up-to-date relationship data to support organizational needs.

### **Link to Video**

[https://loom.com/share/eb7eda81fcd241128f6e383773817a9b?src=composer](https://loom.com/share/eb7eda81fcd241128f6e383773817a9b?src=composer)

## **QA Steps: Steps to Reproduce the Bug in Education Cloud**

### **Environment:**

* **Platform:** Education Cloud  
* **Objects Involved:**  
  * Account  
  * Account Relationship  
  * Contact  
  * Contact Relationship  
  * Custom Object: Contact Account Relationship (CAR)  
* **Device:** Not specified  
* **Browser:** Not specified  
* **OS:** Not specified

### **Steps to Reproduce:**

1. **Access the Screen Flow:**  
   * Navigate to the screen flow component on either a Person Account or a standard Account record.  
2. **Choose Relationship Type:**  
   * Select whether you want to create a relationship from a person to another person or to an organization.  
3. **For Person to Person Relationship:**  
   * The contact name will auto-fill for the person on the account.  
   * Enter the name of the related contact.  
   * Select the relationship type from the available options.  
   * A formula field will provide guidance on the relationship being created.  
   * Submit the form.  
4. **Check for Existing Relationship:**  
   * The system will check for an existing active Contact Contact Relationship (CCR) between the two individuals.  
   * If an active relationship of the same type exists, an error message will appear, indicating that a CCR is already active.  
5. **For Person to Organization Relationship:**  
   * The contact name will auto-fill on the left side.  
   * Enter the organization name.  
   * Input the start and end dates for the relationship.  
   * Select the contact's relationship to the account from a picklist.  
   * Submit the form.  
6. **Check for Existing Organization Relationship:**  
   * The system will check for an existing active Contact Account Relationship (CAR) between the person and organization.  
   * If an active relationship of the same type exists, an error message will appear.  
7. **For Organization to Organization Relationship:**  
   * Similar to the previous steps, input the required details for the organization-to-organization relationship.  
   * The system will check for existing active Account Account Relationships (AAR) and display an error if one exists.  
8. **Observe Automation Behavior:**  
   * Note that the automation for updating the active status of relationships may not function correctly, leading to potential inconsistencies in the relationship records.

### **Expected Outcome:**

* Successful creation of relationships without errors, provided there are no existing active relationships of the same type.

### **Actual Outcome:**

* Errors occur when attempting to create a new relationship if an active relationship already exists, which is expected. However, inconsistencies in the automation for updating active statuses may lead to incorrect relationship states.

### **Additional Notes:**

* Ensure that the automation flows for managing relationships are functioning correctly to avoid orphaned relationships or incorrect active statuses.

### **Link to Video**

[https://loom.com/share/eb7eda81fcd241128f6e383773817a9b?src=composer](https://loom.com/share/eb7eda81fcd241128f6e383773817a9b?src=composer)

## **Code Doc: Education Cloud Relationship Objects Automation Documentation**

This document outlines the automation and screen flow for managing relationship objects within Education Cloud. The automation facilitates the creation and maintenance of various relationship records, including person-to-person, person-to-organization, organization-to-person, and organization-to-organization relationships.

### **Overview of Relationship Objects**

The automation works with four main objects:

1. **Account** (standard)  
2. **Account Relationship** (standard)  
3. **Contact** (standard)  
4. **Contact Relationship** (standard)  
5. **Contact Account Relationship** (custom)

The custom object, **Contact Account Relationship (CAR)**, is used to manage relationships that require unique start and end dates, as the standard **Account Contact Relationship (ACR)** does not allow duplicates.

### **Screen Flow for Creating Relationships**

The guided screen flow is designed to create relationships based on the context of the record being viewed (Person Account or Organization Account). The flow supports the following paths:

1. **Person to Person**  
   * Pre-fills the contact name for the person on the account.  
   * Prompts for the related contact and relationship type.  
   * Validates existing active relationships to prevent duplicates.  
2. **Person to Organization**  
   * Pre-fills the contact name and prompts for the organization account name.  
   * Collects start and end dates and the relationship type.  
   * Creates a **Contact Account Relationship** (CAR) and updates the associated **Account Contact Relationship** (ACR).  
3. **Organization to Organization**  
   * Similar to the person-to-organization flow but focuses on account-to-account relationships.  
   * Validates existing active relationships and creates an **Account Account Relationship** (AAR) if no duplicates exist.

### **Automation Processes**

The following automation processes are triggered during the creation and management of relationship records:

#### **1\. Contact Contact Relationship (CCR) Automation**

* **Before Save:**  
  * Updates the active checkbox based on the start and end date.  
* **After Save:**  
  * Creates and syncs reciprocal relationships when a CCR is created.  
  * Updates inverse relationships if the "Keep in Sync" checkbox is true.  
* **On Delete:**  
  * Deletes reciprocal relationships to prevent orphaned records.

#### **2\. Account Account Relationship (AAR) Automation**

* Identical to CCR automation, with the same before save, after save, and on delete processes.

#### **3\. Contact Account Relationship (CAR) Automation**

* **Before Save:**  
  * Updates the active checkbox and sets a duplicate key to prevent duplicates.  
* **After Save:**  
  * Updates the household account field if the relationship type is "Household Member."  
  * Creates a person employment record if the relationship type is "Employee."  
  * Updates the ACR based on changes to the CAR.  
* **On Delete:**  
  * Similar to CCR automation, checks if roles need to be removed or if the ACR should be deleted.

### **Conclusion**

This documentation provides a comprehensive overview of the automation and screen flow for managing relationship objects within the Education Cloud. By utilizing a combination of standard and custom objects, the system ensures accurate tracking and management of relationships while preventing duplicates and maintaining data integrity.

### **Link to Video**

[https://loom.com/share/eb7eda81fcd241128f6e383773817a9b?src=composer](https://loom.com/share/eb7eda81fcd241128f6e383773817a9b?src=composer)

