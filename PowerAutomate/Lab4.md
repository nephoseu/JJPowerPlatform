---
lab:
    title: '[Lab 04] Using AI Builder in Power Automate'
    module: ' Power Automate'
---
# LAB 4 - Using AI Builder in Power Automate

Task 1:
-------
Build and use AI models to enhance user experience in workflows
==========================================================================

In this task, you will build and use AI models to enhance user experience in workflows.

1.  Open a new web browser and then go to [https://make.powerautomate.com](https://powerautomate.microsoft.com/?azure-portal=true). Sign in if needed and then make sure that you're in the correct environment.
    
2.  In the left navigation pane, select **AI hub**, then select **AI models** near the middle of the screen.
    
    ![Screenshot showing the AI hub menu expanded and the AI models option selected.](img/6-08.png)
    
    >:information_source:**Note**
    >A prompt may appear, stating that you need to get **AI Builder**. You can opt in for a free, 30-day trial, which starts automatically after you complete these steps. Select the **Start trial** button.
    
    ![Screenshot showing the Start trial button.](img/6-09.png)
    
3.  A prebuilt invoice processing model is available for you to use for processing most invoices directly. However, for this training, you learn how to build your own custom model. From the models section, select the **Document Processing** model. The model should also say **Extract custom information from documents**. If your model results are filtered by **Most popular**, then it's the second result.
    
    ![Screenshot showing the Document processing AI model.](img/6-10.png)
    
4.  From the **Extract custom information from documents** dialog, select the **Create custom model** button located in the lower-right corner.
    
    ![Screenshot showing the Create custom model button.](img/6-11.png)
    
5.  Select the **pencil** icon to the left of the model name to begin editing. In the **Model name** field, name the model as `Enter invoice information AI model`. Select the **Rename** button.
    
    ![Screenshot showing the Rename button.](img/6-12.png)
    
6.  Select **Fixed template documents** and then select **Next**.
    
    ![Screenshot showing the Structured documents option selected.](img/6-12.png)
    
7.  Create four fields for your AI model. Select the dropdown menu next to the **\+ Add** button and then select the **Text field** option.
    
    ![Screenshot of the Choose information to extract section, showing the Add and Text field options.](img/6-13.png)
    
8.  Within the **Text field** dialog, in the **Name** field, enter `Bill to`. Select **Done**.
    
    ![Screenshot showing Bill to entered in the Name field.](img/6-14.png)
    
9.  Repeat these steps until you add the following four fields. Keep in mind that you already added the **Bill to** field.
    
    *   Bill to
        
    *   Contact
        
    *   Date
        
    *   Total
        
    
    ![Screenshot showing the newly added fields.](img/6-15.png)
    
10.  After you add all four fields, select the **Next** button in the lower part of the screen.
    
11.  Collections allow for the grouping of documents for a particular organizer, customer, or counterparty. Create a collection for Contoso by selecting the **New collection** button.
    
![Screenshot showing the New connection button.](img/6-16.png)
    
12.  Select **Collection 1** and then rename it to `Contoso Coffee Shop`.
    
![Screenshot showing the collection renamed to Contoso Coffee Shop.](img/6-17.png)
    
13.  Select the plus (**+**) sign in the center of the collection and then select the **Add documents** button to upload your sample PDF files from the lab resources folder.
    
![Screenshot showing the Add documents button.](img/6-18.png)
    
14.  For this task, you upload the files from **local storage/source**. (Your local storage might be named something different than the one shown in the following figure. For this demonstration, the local storage is called **My device**.)
    
![Screenshot showing the Select source dialog.](img/6-19.png)
    
You need a set of documents you are going to work on. Download the documents from this [LINK](https://github.com/nephoseu/JJPowerPlatform/raw/main/Documents.zip), extract them and save them on a local disk.  Select the following documents from your local storage by locating them within the file you saved and then holding the **Ctrl** key and selecting them. Then, select **Open**.
    
*   Contoso\_INVOICE\_(Fabrikam\_UK).pdf
        
*   Contoso\_INVOICE\_(Litware\_CAN).pdf
        
*   Contoso\_INVOICE\_(Proseware\_NY).pdf
        
*   Contoso\_INVOICE\_(TailSpin).pdf
        
*   Contoso\_INVOICE\_(WingTip).pdf
        
    
![Screenshot showing the selected files.](img/6-20.png)
    
15.  Locate and ensure that the five PDF files that are used for this training are selected. Then, select the **Upload 5 documents** button located in the lower part of the **Upload documents** dialog.
    
![Screenshot showing the Upload 5 documents button.](img/6-21.png)
    
16.  After the documents are uploaded, a success message appears, similar to the one in the following figure. Select **Done** to continue.
    
![Screenshot of the Upload documents screen with the success message and showing the Done button.](img/6-22.png)
    
17.  In the **Add documents** dialog, select the **Next** button.
    
![Screenshot of the Add documents dialog showing the Next button.](img/6-23.png)
    
18.  After the system finishes the loading process, you need to tag your documents. Tag the documents one by one, to the correct value of the corresponding fields so that you can teach AI Builder how to extract values from this form example.
    
19.  Ensure that you're currently viewing the first document. By using a drag-to-highlight method, highlight the **Bill to** contact within the document (don't include "Bill to" in your highlight, only highlight the contact). After you highlight the contact in the document, a menu with field options will appear.
    
20.  Select the **Bill to** field option from the menu. The system should tag the document information to the **Bill to** field within the list to the right of the screen. A green check mark appears to confirm the tag.
    
![Screenshot showing the Bill to field being tagged.](img/6-24.png)
    
21.  Use the same process to highlight the **Contact** information within the first document. Then, from the field menu that appears, select the **Contact** field. A green check mark appears in the list to signify that the tag is made within this document.
    
![Screenshot showing the Contact field being tagged.](img/6-25.png)
    
22.  Repeat the previous steps to tag the **Date** and **Total** information from the first document to the proper field. In the upper part of the screen, the first document shows as shaded with a blue color. This shading indicates that all possible tags within this document are made. Your screen should resemble the following figure.
    
![Screenshot showing the tagged fields.](img/6-26.png)
    
23.  In the upper portion of your screen, use the arrows to switch to the next document. Repeat the same process to tag the correct information within the document to the proper field. Repeat this step for the remaining documents until all five documents show as shaded in blue, indicating that all possible tags are made within each document.
    
![Screenshot showing the tagged documents.](img/6-27.png)
    
>:information_source:**Note**
>Select only the field value without the field title from the document. For example, select **Jan 15, 2019** and then tag it as **Date**.
>If you've mistakenly tagged a field, you can right-click the field from the list to the right of the screen and then select the **Remove tag** option.
    
24.  After you finish making all possible tags within the five documents, select the **Next** button located in the lower left of the screen.
    
![Screenshot showing the Next button.](img/6-28.png)
    
25.  Now, you're ready to train your AI Builder model. To do so, select the **Train** button located in the lower left of the screen. This process might take a few minutes to complete.
    
![Screenshot showing the Train button.](img/6-29.png)
    
26.  The window in the following figure appears while the model is training. Select the **Go to models** button.
    
![Screenshot of the Your model is training dialog, showing the Go to models button.](img/6-30.png)
    
27.  After the AI Builder model training is complete, the status changes to **trained**. Select the **title** of the model to gain access to more options. Here you can **publish** your AI Builder model by selecting **Publish**.
    
>:information_source:**Note**
>Publish your model when you want to make it available to users in your Power Automate environment.
    
![Screenshot showing the Publish button.](img/6-31.png)
    
28.  Now you have an AI Builder model trained and published. Next, you use this AI Builder model that you trained in your automation.
29. Create a new flow with tirgger **When email arrives **.
        
34.  Select **+** to add a new step to the flow. After selecting the plus sign, select **Add an Action** located under the **+** that was selected.
    
![Screenshot showing the New step button in the flow.](img/6-38.png)
    
35.  Within the search bar, search for `extract information from` and then select **Extract information from documents - AI Builder** from the list.
    
![Screenshot showing the Extract information from documents action.](img/6-39.png)
    
>:information_source:**Note**
>You may need to sign in to create a connection to Microsoft Dataverse. If so, select an **Authentication** type, then select **Sign in**.
    
36.  From the **AI model** dropdown menu, select **Enter invoice information AI model**.
    
37.  From the **Form type** dropdown menu, select **JPEG Image**.
    
38.  Select the **Form** field, and then select the blue **lightning bolt** button on the side of the pane. After selecting the **lightning bolt** button search for `Attachments Content` in the **Dynamic Content**. Then select **Attachments Content**.
    
![Screenshot showing Attachments Content highlighted in the Dynamic content pane.](img/6-40.png)
    
>:information_source:**Note**
>After you've populated the **Form** field with the **Attachments Content** array, an **Apply to each** loop, named "**For each**", is added automatically to the flow designer around the AI Builder action. This result occurs because the **Attachments Content** array could include more than one attachment, so the **Apply to each** control ensures that the AI Builder model processes each file attachment separately. In this lab, you only need to send a single attachment.
    
39.  The **Apply to Each** loop might be collapsed. To expand it, select the down arrow next to the title.
    
40.  Select the AI Builder action to expand the card for more details. Change the flow name by double-clicking the name in the upper left of the screen and then entering the new name as `Enter invoice information flow`. In the upper-right corner of the screen, select **Save**.
    
![Screenshot showing Enter invoice information entered for the name and the Save button highlighted.](img/6-41.png)
    
41.  To verify the AI Builder model processing result, you add another action to send yourself a verification email to the sender. This email acknowledges that the invoice was received. Add another action by selecting the **+** button and then **Add an Action** under the AI Builder action.
    
![Screenshot showing the Add an action button under the AI Builder action.](img/6-42.png)
    
42.  Within the search box, search for `send an email`. Then, from the list, find and select **Send an email (V2)** under the Office 365 Outlook action options.
    
![Screenshot showing the Send an email V 2 flow action.](img/6-43.png)
    
43.  In the **To** field, select the box and select **Enter custom value**. This causes the **lightning bolt** button to appear. Select that and it takes you to the Dynamic Content search bar. In the search bar, search for `from` and then select **From - The mailbox owner and sender of the message**.
    
![Screenshot showing the From field selected from the Dynamic content pane.](img/6-44.png)
    
44.  Fill in the rest of the fields for the email step by using the following values and information:
    
*   **Subject** field - Enter `Thanks for sending the invoice`
        
*   **Body** field - Enter the following content:
        
        `We received an invoice with the details below:`
        
        `Total:` (enter the **Total value** from the **Dynamic content** pane)
        
        `Date:` (enter the **Date value** from the **Dynamic content** pane)
        
        `Contact:` (enter the **Contact value** from the **Dynamic content** pane)
        
        `Bill to:` (enter the **Bill to value** from the **Dynamic content** pane)
        
        `We will process and get back to you shortly.`
        
        `Thanks,`
        
        `Contoso Coffee Shop`
        
    
>:information_source:**Note**
>To find the values for the body of the email, search in the **Dynamic content** pane (the lightning bolt icon) for each value. The values will appear as written in the previous step.
    
![Screenshot showing the email content.](img/6-45.png)
    
45.  After you finish filling in the information, select **Save** in the upper-right corner of the screen.
    
46.  Select the **back** button in the upper left of the screen, before the flow name, to return to the flow detail page.
    
![Screenshot showing the back button.](img/6-46.png)
    
47.  Trigger the flow to test by sending an email. In a separate web browser tab, open the Office 365 Outlook app. Sign in if needed.
    
48.  Compose a new email with the following settings and information:
    
*   **To** field - (email address of the user identity that you're using in this lab)
        
*   **Subject** field - `New invoice`
        
*   **Attachments** - new-invoice.jpg _(from the lab resource files)_
        
    
>:information_source:**Note**
>This attachment can be in JPG or PDF format; the AI Builder model can process both. This task uses a JPG file for example purposes.
    
>:information_source:**Note**
>Your email signature might be viewed as an attachment, and it will block this flow logic unless you add more validation. We recommend that you try to send the email without your signature.
    
49.  Send the email. The flow should be triggered to run automatically.
    
50.  Return to the flow detail page in the original tab. Notice that a new run starts. You might need to select the **Refresh** button a few times to view the new run history.
    
![Screenshot showing the flow run status and the Refresh button.](img/6-47.png)
    
51.  Select the new run to view its details. It shows whether your flow ran successfully or not.
    
![Screenshot showing the flow run result.](img/6-48.png)
    
52.  You can also select the title to expand the **Apply to each** action and the **AI Builder** action to view the output from the **Predict** action. It should contain the real time data parsed from the email attachment file. 
    
![Screenshot showing the flow run.](img/6-49.png)
    

You should also receive an acknowledgment email with the AI Builder process results against the JPG invoice file.

![Screenshot showing the email that the flow sent.](img/6-50.png)

-------
## Congratulations!

Now you've learned how to use AI Builder in Power Automate, a low-code AI technology that can help you understand and pull data information automatically from the email attachment invoice file. You also learned how to use the data from the invoice file as inputs for the desktop flow to use when it enters information in the management app system.

    
