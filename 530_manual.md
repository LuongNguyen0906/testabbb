# @lab.Title

In this lab you’ll work with Microsoft Copilot Studio to build your first copilot using Generative answers, you’ll then publish this copilot to Microsoft Teams.

In the second half of this workshop, you'll extend your copilot with a custom connector that you’ll build in Visual Studio, publish this as custom connector and then add this as a plug in your Copilot.

The green text with the +++icon+++ can be clicked on and will be typed automatically into the VM, For example, please click in the password text box and then click the password: +++@lab.VirtualMachine(WRK530).Password+++

> [!note] To ensure text is entered accurately avoid interacting or clicking in the VM until the text has finished being typed

===

# Build Your First Copilot

To start you're going to build your very first copilot powered by Generative answers.

1. Open Microsoft Edge and navigate to

    [https://copilotstudio.microsoft.com](https://copilotstudio.microsoft.com)

2. Log in with

    **Username:** +++@lab.CloudCredential(CSBatch1).UserPrincipalName+++

    **Password:** +++@lab.Variable(TAP)+++

<!-- 3. If you see a message about needing to setup additional security like is shown below, select **Ask later**

    !IMAGE [pic1_official.png](instructions273634/pic1_official.png) -->

3. If you see a welcome screen like is shown below, select the country/region that you’re in from the dropdown and select Get Started

    !IMAGE [pic2.png](instructions273634/pic2.png)
4. Click the Environment drop down in the top right and then select the Dev environment **@lab.CloudCredential(CSBatch1).EnvironmentName**

    !IMAGE [step3.png](instructions273634/step3.png)
5. If you see a welcome message as shown in the screenshot below, select Skip.

    !IMAGE [step6.png](instructions273634/step6.png)
6. In the left nav click **+ Create** button to start creating a new copilot

    !IMAGE [step7.png](instructions273634/step7.png)
7. Click **New copilot**

    !IMAGE [step8.jpg](instructions273634/step8.jpg)
8. While we could use natural language to setup the copilot for this exercise, we will skip directly to the configuration Click the Skip to configure button

    !IMAGE [step9.jpg](instructions273634/step9.jpg)
9. Give your copilot a name then click the **+ Add knowledge**

    !IMAGE [step10.jpg](instructions273634/step10.jpg)
10. In the Add available knowledge sources dialog click the **Public websites** button

    !IMAGE [step11.jpg](instructions273634/step11.jpg)
11. In the Add public websites dialog enter +++www.microsoft.com+++ then click the **Add** button

    !IMAGE [step12.jpg](instructions273634/step12.jpg)
12. With the new knowledge source added click the \*\*Add \*\* button in the bottom right of the dialog to include this in your new copilot

    !IMAGE [step13.jpg](instructions273634/step13.jpg)
13. With the dialog closed confirm the name and the knowledge source of your new copilot are correct then in the top right click the **Create** button

    !IMAGE [step14.png](instructions273634/step14.png)
14. In the copilot test window enter “what is Microsoft Copilot Studio” and press enter

    > [!note] If you don't see the test copilot pane you can open this by clicking on Test button in the top right corner of the screen to open the test pane

    !IMAGE [step15.jpg](instructions273634/step15.jpg)
    !IMAGE [step15part2.jpg](instructions273634/step15part2.jpg)

Congratulations! you just built your first Copilot powered by generative answers.

===

# Publishing Your Copilot

Now that you have confirmed your copilot is working as expected let’s publish the copilot this allows you to then use your copilot in other channels like teams or even Microsoft 365.

16. Click the **Publish** button in the top right-hand corner

    !IMAGE [step16.jpg](instructions273634/step16.jpg)
17. Click the **Publish** button to publish your Copilot

    !IMAGE [step17.jpg](instructions273634/step17.jpg)

    The following dialog will be displayed you can close this and your copilot will finish publishing in the background

    !IMAGE [step17part2.jpg](instructions273634/step17part2.jpg)
18. Now that it’s published, we need to make this available to use within Microsoft Teams. Select the **Channels** tab in the top menu

    !IMAGE [step18.png](instructions273634/step18.png)
19. Under the list of channels, select **Microsoft Teams**

    !IMAGE [step19.png](instructions273634/step19.png)
20. In the panel that opens on the right-hand side, select **Turn on Teams**

    !IMAGE [step20.png](instructions273634/step20.png)
21. After Teams is turned on, you’ll get a message letting you know the channel was added. Select **Open copilot to add your new Copilot to Teams**

    !IMAGE [step21.png](instructions273634/step21.png)
22. Choose **Use the web app instead**

    !IMAGE [step22.png](instructions273634/step22.png)
23. You’ll see a preview of your Copilot. Select **Add**

    !IMAGE [step23.png](instructions273634/step23.png)
24. Your Copilot is now added and accessible in Microsoft Teams. Test your Copilot by asking +++What are the specs for the latest Surface laptop?+++ in the prompt input and press Enter

    !IMAGE [step24.png](instructions273634/step24.png)

Congratulations! You’ve now built and published a Copilot to Microsoft Teams!

===

# Extending Copilot With Custom Connectors

In the last portion of the workshop, we showed you how to build a copilot that uses Generative Answers as a source of information.

Now you'll step through how to build a custom connector that can be used as a plug in for your Copilots. Plugins allows Copilot to work with other systems expanding its capabilities beyond answering questions.

In this example we will work with an API that can look up order details and then extend that scenario by adding a method to update the delivery address of a returned order.

1. Open Windows Explorer and open to +++**D:\LabFiles\ContosoApiApp\ContosoApiApp**+++ and open the **ContosoApiApp.sln** file.
2. This is the solution we will be building on to create a custom connector for our copilot. Before continuing press **Ctrl+ Shift + B** to build the solution

    !IMAGE [step26.jpg](instructions273634/step26.jpg)
3. While our app is technically set to run in HTTPS we are going to test it locally first Click the arrow next to **https** in the tool bar and select **http**

    > [!note] We will switch this back before publishing this to Microsoft Copilot Studio

    !IMAGE [step27.jpg](instructions273634/step27.jpg)
4. Click the **Run** button to run your application

    !IMAGE [step28.jpg](instructions273634/step28.jpg)
5. Once the application is running it will appear in a new browser window showing the details about the objects and methods you can test.

    !IMAGE [step29.jpg](instructions273634/step29.jpg)
6. Click the **Get** method and then click the **Try it out** button to test the get method

    !IMAGE [step30.jpg](instructions273634/step30.jpg)
7. Enter an order number (any number will work) then click the **Execute** button

    !IMAGE [step31.jpg](instructions273634/step31.jpg)
8. Scroll down to see the response returned from the **GetOrderDetails** method

    !IMAGE [step32.jpg](instructions273634/step32.jpg)
9. Close the browser window to stop the App running

===

# Add a New Method To The Connector

Now you could publish the connector as is, but before we do lets add a new method that can update the delivery address for the order Swagger is being used to generate the comments for these methods, because of this when adding a new method we first need to provide information for what that method does, this information is also what the generative action engine will use to determine what method to call.

1. Add the following code after the comment that says **Start Exercise Space**

    !IMAGE [step34.jpg](instructions273634/step34.jpg)

    **Code:**

    ```
    [SwaggerOperation(OperationId="UpdateDeliveryAddress",
    Summary="Update delivery address",
    Description= "Update the delivery address for the order number provided then return the updated delivery details" )]
    ```
2. After the SwaggerOperation add in the definition for the HttpPost controller path

    **Code:**

    ```
    [HttpPost(Name = "/UpdateDeliveryAddress/{orderNumber}/{street}/{city}/{state}/{zipcode}")]
    ```
3. Add a new Public method that returns an Order called **UpdateDeliveryAddress**

    **Code:**

    ```
    public Order UpdateDeliveryAddress()
    {
    }
    ```
4. Add the following **SwaggerParameters** to the **UpdateDeliveryAddress**

    **Code:**

    ```
    [SwaggerParameter("The Order number to be updated", Required= true)] string orderNumber,
    [SwaggerParameter("The updated Street Address", Required=true)] string street,
    [SwaggerParameter("The updated City name",Required= true)] string city,
    [SwaggerParameter("The updated State", Required=true)] string state,
    [SwaggerParameter("The udpated Zip Code", Required=true)] string zipcode
    ```

    The method should look similar to the image below

    !IMAGE [step37.jpg](instructions273634/step37.jpg)
5. Click **Yes** on the **Trust ASP.NET Core SSL Certificate** dialog

    !IMAGE [step69.jpg](instructions273634/step69.jpg)
6. Click **Yes** on the security warning dialog to install the certificate

    !IMAGE [step70.jpg](instructions273634/step70.jpg)
7. With the method defined add the following code between the curly braces

    **Code:**

    ```
    Order orderToUpdate = GetOrderDetails(orderNumber);
    orderToUpdate.OrderDetails.ShippingAddress.Street = street;
    orderToUpdate.OrderDetails.ShippingAddress.City = city;
    orderToUpdate.OrderDetails.ShippingAddress.State = state;
    orderToUpdate.OrderDetails.ShippingAddress.ZipCode = zipcode;
    return orderToUpdate;
    ```

    the final code should look similar to the below

    !IMAGE [step38.jpg](instructions273634/step38.jpg)
8. Run your application locally again by clicking the **run** button

    !IMAGE [step39.jpg](instructions273634/step39.jpg)
9. There will be a new Post method available in the ContosoApiApp

    !IMAGE [step40.jpg](instructions273634/step40.jpg)
10. Click the new **Post \*\*method and click \*\* Try it out**

    !IMAGE [step41.jpg](instructions273634/step41.jpg)
11. Enter the required details and click **Execute** to test

    !IMAGE [step42.jpg](instructions273634/step42.jpg)
12. Scroll down to see the response and confirm the method is responding as expected

    !IMAGE [step43.jpg](instructions273634/step43.jpg)
13. Close the browser window to stop the application

===

# Adding Connector To Microsoft Copilot Studio

With the connector built and the new post method added it's time to add this to Microsoft Copilot Studio so it can be used by the Generative Actions engine.

19. Before publishing the connector, we need to change the run mode from http back to https, click the arrow next to **http** and select **https**

    !IMAGE [step45.jpg](instructions273634/step45.jpg)
20. In the solution explorer on the right side, **Right click>Connected Services>Add>Microsoft Power Platform**

    !IMAGE [step46.jpg](instructions273634/step46.jpg)
21. In the top right of the **Connect to Microsoft Power Platform** dialog click **Sign in>Work, School or personal account** then use your tenant credentials to login to connect to the Power Platform.

    Username: +++@lab.CloudCredential(CSBatch1).UserPrincipalName+++

    Password: +++@lab.Variable(TAP)+++

    !IMAGE [step47.jpg](instructions273634/step47.jpg)
22. Check to make sure your development environment (@lab.CloudCredential(CSBatch1).EnvironmentName) is selected and that the **Common Data Services Default Solution** is selected then click the **+** button to create a new custom connector

    !IMAGE [step48.jpg](instructions273634/step48.jpg)
23. Accept *\*Power Platform environment\** and **Custom connector name** provided then click **Create**

    !IMAGE [step49.jpg](instructions273634/step49.jpg)
24. Click the **+** button to create a public dev tunnel this will allow us to debug the connector when it's called from our Copilot

    !IMAGE [step50.jpg](instructions273634/step50.jpg)
25. Give your Dev tunnel a name then click the **Ok** button

    !IMAGE [step51.jpg](instructions273634/step51.jpg)
26. Click **Next** to see a summary of the changes to be made

    !IMAGE [step52.jpg](instructions273634/step52.jpg)
27. Click Finish to create the connector

    !IMAGE [image.png](instructions273634/image.png)
28. Wait for the connector to be created then click **Close**

    !IMAGE [step54.jpg](instructions273634/step54.jpg)

===

# Adding the Contoso Plugin to your Copilot

30. Reopen the **Microsoft Edge** window from the start of the lab and click on the Copilot Studio tab
31. Click on the **Settings** button on the right of the top nav bar

    !IMAGE [step56.jpg](instructions273634/step56.jpg)
32. Click on **Generative AI** in the left navigation

    !IMAGE [step57.jpg](instructions273634/step57.jpg)
33. Confirm that the **Generative** option is selected then click **Save**

    !IMAGE [step58.png](instructions273634/step58.png)
34. Click on your copilot in the left nav to return to the copilot overview page

    !IMAGE [step59.jpg](instructions273634/step59.jpg)
35. Click on **Actions** in the top nav

    !IMAGE [step60.jpg](instructions273634/step60.jpg)
36. Click the **+ Add an action** button to add a new action

    !IMAGE [step61.jpg](instructions273634/step61.jpg)
37. Enter **Contoso** in the search field and click **Search**

    !IMAGE [step62.jpg](instructions273634/step62.jpg)
38. You will see 2 actions returned from your search, each of these represents one of the methods in the connector we just published from Visual Studio. Click **Get Order Details** to begin adding this action to your copilot

    !IMAGE [step63.jpg](instructions273634/step63.jpg)
39. Once the connector has loaded, in the End user authentication dropdown, select **Copilot author authentication** then click Next

    !IMAGE [step64.png](instructions273634/step64.png)
40. Select **Outputs (15)** to switch to the outputs.

    !IMAGE [actions-select-outputs.png](instructions273634/actions-select-outputs.png)
41. Select **Edit outputs** to edit the outputs.

    !IMAGE [actions-edit-outputs.png](instructions273634/actions-edit-outputs.png)
42. Scroll all the way down and check the checkbox before **Respond to the user after running this action**.

    !IMAGE [actions-respond-to-user.png](instructions273634/actions-respond-to-user.png)
43. This will show you that the action will send a message to the user that is dynamically generated by AI. Click **Save**.

    !IMAGE [actions-dynamically-generated-ai-save.png](instructions273634/actions-dynamically-generated-ai-save.png)
44. Click **Next** to connect to the ContosoApiApp and add the connection

    !IMAGE [step65.jpg](instructions273634/step65.jpg)
45. Click **Finish** to complete adding the plugin to the copilot

    !IMAGE [step66.jpg](instructions273634/step66.jpg)
46. Repeat steps 34-45 to add the other plugin from the ContosoApiApp once complete you should see both plugins listed as below

    !IMAGE [step67.jpg](instructions273634/step67.jpg)
47. Return to Visual Studio and click the **Run** button next to the HTTPS flag to run your application in HTTPS

    !IMAGE [step68.jpg](instructions273634/step68.jpg)

<!-- 44. Click **Yes** on the **Trust ASP.NET Core SSL Certificate** dialog

    !IMAGE [step69.jpg](instructions273634/step69.jpg)

45. Click **Yes** on the security warning dialog to install the certificate

    !IMAGE [step70.jpg](instructions273634/step70.jpg) -->

46. Click **Yes** on the **Microsoft Visual Studio** dialog to trust the IIS Express SSL certificate.

    !IMAGE [step71.jpg](instructions273634/step71.jpg)
47. Click **Yes** on the final security warning dialog to install the IIS cert

    !IMAGE [step72.jpg](instructions273634/step72.jpg)
48. Once the application is running a new browser window will open with a warning that you are about to connect to a developer tunnel click **Continue** to open your running application in Microsoft edge

    !IMAGE [step73.jpg](instructions273634/step73.jpg)
49. With your application running return to Microsoft Copilot Studio in the **Test Copilot** pane click the Map button on the right to open the conversation map console

    !IMAGE [step74.jpg](instructions273634/step74.jpg)
50. Now you can test your Copilot's new capabilities and see in real time how it is making calls to the plugins you just added. Enter **What's my order details** and click send

    !IMAGE [step75.jpg](instructions273634/step75.jpg)
51. In the **Conversation Map** pane, you can see how Copilot is pulling together the actions needed to complete your request. However, as you have not provided an order number to make the call to the service it has formulated a response to ask you for the missing details

    !IMAGE [step76.jpg](instructions273634/step76.jpg)
52. Enter an order number and click send

    !IMAGE [step77.jpg](instructions273634/step77.jpg)

    You'll see the order number is passed to the plugin and the results are returned to your copilot

    !IMAGE [step78.jpg](instructions273634/step78.jpg)
53. Click the reset button to start a new test session

    !IMAGE [step79.jpg](instructions273634/step79.jpg)
54. Enter **Update my delivery address for order 123456 to 1 Microsoft Way, Redmond 98052 WA** and click send

    !IMAGE [update-delivery-address.png](instructions273634/update-delivery-address.png)
55. Once again Copilot will find the correct action to fulfil the request and step through collecting the information needed to make the call

    !IMAGE [step81.jpg](instructions273634/step81.jpg)
56. Provide the updated address details to Copilot as it requests them

Congratulations! You have successfully created a new copilot, built and deployed a custom connector using Visual Studio!