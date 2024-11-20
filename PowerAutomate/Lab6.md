---
lab:
    title: '[Lab 06] Integration of Power Automate with the Canvas App'
    module: ' Power Automate'
---
# LAB 6 - Integration of Power Automate with the Canvas App

In this lab, you'll learn how create and trigger a flow using canvas apps.

You're going to create a trial environment that will include a Dataverse database, and the sample data used in this lab.

1.  Go to [Power Platform admin center](https://admin.powerplatform.microsoft.com/).
    
2.  Select **Environments**.
    
3.  Select **New**.
    
4.  Name the environment **Dataverse Trial**.
    
5.  Select **Trial** for environment type.
    
6.  Toggle **Create Database** to **Yes**.
    
7.  Select **Next**.
    
8.  Toggle **Deploy Sample Apps and Data** to **Yes**.
    
9.  Select **Save**.
    

Your trial environment will now be created, including a Dataverse database and sample data.

## Task 1 - Create a canvas app

In this lesson, we'll create an app to search, view, and create customer accounts using the **Accounts** table in Dataverse.

1.  Start by creating a **blank canvas app**.
    
2.  Select **Create a gallery**.
    
    ![Create a gallery](img/build-a-canvas-app-4.png "Create a gallery")
    
3.  Select **Accounts** table.
    
4.  Stretch the gallery to the bottom of the screen, and add a label to the top with the text **Accounts**. And then, update the other properties as listed below.
    
    Expand table
    
    | Property | Value |
    | --- | --- |
    | Font | Open Sans |
    | Font size | 21  |
    | Font weight | Bold |
    | Text alignment | Center |
    | Auto height | Off |
    | Line height | 1.2 |
    | Overflow | Hidden |
    | Display mode | Edit |
    | Visible | On  |
    | Position (X, Y) | 0, 0 |
    | Size (Width, Height) | 640, 71 |
    | Padding | 5 Top, 5 Bottom, 5 Left, 5 Right |
    
    ![Update gallery properties](img/build-a-canvas-app-6.png "Update gallery properties")
    
5.  Add an **Add** icon to the top-right of the screen by selecting **Insert** > **Icon** > **Add**. And then, update the properties of the icon to color white and padding of 5 from all sides.
    
    ![Add an Add icon](img/build-a-canvas-app-7.png "Add an Add icon")
    
6.  From the top-left side of the screen, select **New screen** > **Form**.
    
    ![Add new form](img/build-a-canvas-app-8.png "Add new form")
    
7.  Update the title of the form to **New Account**, and select the data source as **Accounts** from the pane on the right-side of the screen.
    
    ![Update title and select data source](img/build-a-canvas-app-9.png "Update title and select data source")
    
8.  Select **Edit fields** on the right-pane.
    
    ![Select edit fields.](img/build-a-canvas-app-10.png)
    
9.  Select **Add field** and add **Email** to the form.
    
    ![Add email field.](img/build-a-canvas-app-11.png)
    
    The email field gets added to the form.
    
    ![The email field gets added.](img/build-a-canvas-app-12.png)
    
10.  Set the default mode of the form to **New**.
    
    ![Default form mode](img/build-a-canvas-app-13.png "Default form mode")
    
11.  Select Screen1 that has the accounts gallery, and set the **OnSelect** property of the **+** icon to `Navigate(Screen2)`.
    
    ![Configure navigation to screen 2](img/build-a-canvas-app-14.png "Configure navigation to screen 2")
    
12.  Select **Insert** > **New screen** > **Blank screen** to add a new screen to the app.
    
13.  Select **Insert** > **Icon**, and then select the Check (badge) icon to add it to the screen.
    
    ![Insert badge icon](img/build-a-canvas-app-16.png "Insert badge icon")
    
14.  Move the icon to the top center of the canvas.
    
    ![Move icon to top-center](img/build-a-canvas-app-17.png "Move icon to top-center")
    
15.  Add a label with text **Account was created successfully!**, and move it under the icon added in the earlier step.
    
    ![Add Account was created successfully label](img/build-a-canvas-app-18.png "Add Account was created successfully label")
    
16.  Add an additional label below the label added in the previous step with text **Send a welcome note to the Customer?**.
    
    ![Send a welcome note to the Customer](img/build-a-canvas-app-19.png "Send a welcome note to the Customer")
    
17.  Add a **Text Input** box by selecting **Insert** > **Input** > **Text Input**. Set the **Mode** of the control to **Multiline**, and default text to **Thank you for creating an account with us. We look forward to serving you!**. And move the control below the label added in the previous step.
    
    ![Add multiline text input control](img/build-a-canvas-app-20.png "Add multiline text input control")
    
18.  Set the **OnVisible** property of **Screen3** to `Reset(TextInput1)`.
    
    ![OnVisible property of screen 3](img/build-a-canvas-app-21.png "OnVisible property of screen 3")
    
19.  Add two buttons to the screen with text **Yes** and **No**, and place them below the input text box added in the previous step.
    
    ![Yes No buttons](img/build-a-canvas-app-22.png "Yes No buttons")
    
20.  Go to the **New Account** form screen, and set the **OnVisible** property of the screen to `ResetForm(EditForm3)`.
    
    ![OnVisible property of New Account form](img/build-a-canvas-app-23.png "OnVisible property of New Account form")
    
21.  Select the check icon on the top-right, and set the **OnSelect** property to `SubmitForm(EditForm3);Navigate(Screen3)`.
    
    ![Navigate to screen 3](img/build-a-canvas-app-24.png "Navigate to screen 3")
    
22.  Select the X button on the top-right, and set the **OnSelect** property to `Back()`.
    
    ![Back function for close](img/build-a-canvas-app-25.png "Back function for close")
    
23.  Go back to **Screen3** by selecting **Screen3** in the tree view.
    
    ![Go to screen 3](img/build-a-canvas-app-26.png "Go to screen 3")
    
24.  Select the **No** button, and set the button's **OnSelect** property to `Navigate(Screen1)`.
    
    ![Navigate to screen 1](img/build-a-canvas-app-27.png "Navigate to screen 1")
    
25.  Select the **Yes** button, on the app authoring menu select **Power Automate**.
    
    ![Select Power Automate fromt he app authoring menu.](img/build-a-canvas-app-28-1.png "Select the Yes button and select Action on the top")
    
26.  Select **Create a new flow** to create a new Power Automate flow.
    
    ![Select Create a new flow.](img/build-a-canvas-app-29-1.png "Select Create a new flow to create")
    


## Task 2 - Create the Power Automate Flow

1.  On the **Create your flow** screen, from the list of instant templates, select **Click a button in Power Apps to send an email**.
    
    ![Select the Click a button in Power Apps to send an email template.](img/create-the-power-automate-flow-1-1.png "select the Click a button in Power Apps to send an email.")
    
2.  Enter a name for the flow as "Flow triggered by Power Apps", and select **Power Apps** as the trigger.
    
    ![Enter a name for the flow](img/create-the-power-automate-flow-2-1.png "Enter a name for the flow")
    
3.  Select **Edit in advanced mode** and then select, **Continue**.
    
    ![Edit the flow in advacned mode](img/edit-advacned-mode.png "Edit in advacned mode")
    
4.  The **To** field and the **Body** field are automatically auto-populated with the following:
    
    *   To: **Sendanemail(V2)\_To**.
    *   Body: **Sendanemail(V2)\_Body**
5.  In **Subject** field, delete **Sendanemail(V2)\_To** and enten **Thank you for your business!** in the **Subject** field.
    
    ![Enter Thank you for your business](img/add-subject.png "Enter Thank you for your business")
    
6.  Select **Save** to save the flow.
    


## Task 3 - Trigger the flow from within the canvas app

1.  Select the **Yes** button > in the **OnSelect** property enter the two parameters for the To email address and the Body of the email as follows:
    

    ```
    FlowtriggeredbyaPowerapp.Run(
       EditForm3.LastSubmit.Email,
       TextInput1.Text
    );
    Navigate(Screen1);
    ```
    
    Note
    
    The email address is picked up from the new account record created on the previous screen. and the body for the email is picked from the text box text captured on this screen.
    
    ![Fill in the two parameters for the To email address](img/onselect-flow.png "Fill in the two parameters for the To email address")
    

## Task 4 - Test the app

Run the app in preview mode. In this test, we'll create a new account by entering details like account name, phone number, city, and email address on the **New Account** screen. On saving the new account details, we'll be prompted to send an email to the customer where we can update the verbiage of the email, and then select **Yes** to send the email. This will trigger the flow, and email will be sent to the email address on the account.

![Run the app in Preview mode](img/test-the-app-1-1.png "Run the app in Preview mode")

![Create a new account by entering details like account name](img/test-the-app-2.gif "Create a new account by entering details like account name")

An email like this should appear in your inbox

![Email like this should appear in your inbox](img/test-the-app-3.png "mail like this should appear in your inbox")


-------
## Congratulations!

You've learned how to create a Canvas App in Power Platform that can trigger a Power Automate flow.

    
