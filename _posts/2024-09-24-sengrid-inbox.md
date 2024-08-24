---
title: "Email Inbox with SendGrid"
date: 2024-09-24
---
<head>
<style>
.container {
  border: 1px solid #dedede;
  background-color: #a39d87;
  color: #000000;
  border-radius: 5px;
  padding: 10px;
  margin: 10px 0;
}
</style>
</head>

<div class="row">
    <div class="col-md-12 header-banner">
        <img src="{{site.baseurl}}/assets/2024-06-24/header.jpg" class="full-width-image" title="Email Inbox with SendGrid" >
    </div>
</div>

# Email Inbox with SendGrid
<span>By: [Shafran Ashraff](https://www.linkedin.com/in/shafran-ashraff-uk/), [Sankalpa Abeygunawardhana](https://www.linkedin.com/in/sankalpaabeygunawardhana/)</span>

## Introduction
SendGrid (also known as Twilio SendGrid) is an open-source SaaS platform that is based in managing transactional and marketing emails. In other words, SendGrid manages different types of emails, such as shipping notifications, real time email features, email newsletters, inbound parse etc. They provide API for developers that allows to pull information about their email program without having to actually log on to SendGrid. Furthermore, users can pull lists, statistics, and even email reports. In addition to this, Users can send email via the web API without using traditional SMTP.

## Implementation
SendGrid is one of the most popular email service option for sending emails from Azure. Azure and SendGrid are so popular because there used to be a free plan with 100 emails per a day limit to Azure users.

Let’s take a quick example:
If you are using Azure Twilio SendGrid Subscription you can send emails, monitoring emails, inbound parse and customize email template outside your Business Code.
Let’s take a quick example:
Go to your [Azure portal](https://portal.azure.com/) and go to marketplace and search to “sendgrid”

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/azure-twillio-sendgrid.jpg" class="full-width-image" title="Twillio Sendgrid in Azure">
        <p>Twillio Sendgrid in Azure.</p>
    </div>
</div>

Click on the “Twilio SendGrid” and Subscribe To Twilio SendGrid. After Subscription it will create a SasS application

After created SaaS application, Click on the created application. Then it will direct to the SendGrid SaaS application

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/azure-sendgrid-saas.jpg" class="full-width-image" title="SendGrid SaaS">
        <p>SendGrid SaaS.</p>
    </div>
</div>

Once you click on the “Open SaaS Account on publisher’s site” link it will be open the SendGrid dashboard as a new tab.


<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/azure-sendgrid-dashboard.jpg" class="full-width-image" title="SendGrid Dashboard">
        <p>SendGrid Dashboard.</p>
    </div>
</div>

When we considering about the SendGrid setup for mailing feature, we must do some couple of changes inside the SendGrid settings. Let’s see how to setup SendGrid for API project.

First you have to copy the API key and store the value in AppSettings.Json file. If you go to Settings – API Key direction, it will return all information of the related API information.

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/azure-sendgrid-apikey.jpg" class="full-width-image" title="SendGrid SaaS">
        <p>SendGrid SaaS.</p>
    </div>
</div>

If you done above step, then you have to verify the sender’s email address. To do this step you must go to Settings - Sender Authentication direction and it will display an interface regarding the Sender Authentication.

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/azure-sendgrid-sender-authentication.jpg" class="full-width-image" title="SendGrid Sender Authentication">
        <p>Sender Authentication.</p>
    </div>
</div>

The next step is you have click on the Verify a Single Sender and it will be opened a drawer for you.

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/azure-sendgrid-create-sender.jpg" class="full-width-image" title="SendGrid Create a Sender">
        <p>Create a Sender.</p>
    </div>
</div>

You have to fill that information and click on the create button. Then SendGrid will send a verification key. Feel free to click on the link. Then SendGrid will verify your email address.

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/azure-sendgrid-create-sender.jpg" class="full-width-image" title="SendGrid Create a Sender">
        <p>Create a Sender.</p>
    </div>
</div>

You have to fill that information and click on the create button. Then SendGrid will send a verification key. Feel free to click on the link. Then SendGrid will verify your email address.

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/azure-sendgrid-sender-varification.jpg" class="full-width-image" title="SendGrid sender verification">
        <p>Sender verification.</p>
    </div>
</div>

Let’s create a Asp.Net core web application and try to send a email through SendGrid.
Open your web solution and go to NuGet package manage and search and install to Send grid.

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/sendgird-nuget-package.png" class="full-width-image" title="SendGrid sender verification">
        <p>Sender verification.</p>
    </div>
</div>

Then, create a method to send an email.

``` c#
public async Task<bool> SendEmail(MailingVM resources)
{
    var key = "your_sendgrid_key"
    var client = new SendGridClient(key);
    var messge = MailHelper.CreateSingleEmail(
        "fromemail@FromEmail.com",
        "toemail@ToEmail.com",
        resource.Subject,
        resource.PlainText, 
        resource.HtmlContent
    );

    var response = await client.SendEmailAsync(message);
    return resonse.IsSuccessStatusCode;
}
```
Call the API via Postman
<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/sendgrid-check-message-postman.jpg" class="full-width-image" title="SendGrid sender verification">
        <p>Sender verification.</p>
    </div>
</div>

The result should be displayed as bellow.
<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/sendgrid-mail-received.png" class="full-width-image" title="SendGrid sender verification">
        <p>Sender verification.</p>
    </div>
</div>

This is the how we send emails via the SendGrid. Moreover, you can add references, Cc, Bcc and attachments through the SendGrid object.
For an example if you want to add attachments you have to add them as a stream.

``` c#
foreach (var item in resource.Files)
{
    var memoryStream = new MemoryStream();
    await item.CopyToAsync(memoryStream);
    memoryStream.Position = 0;

    var attachment = new SendGrid.Helpers.Mail.Attachment()
    {
        Content = Convert.ToBase64String(memoryStream.ToArray()),
        Filename = itme.FileName, 
        Type = mimeTypeMapping.GetMimeType(item.FileName),
        Disposition = "attchment"
    };
    attachments.Add(attachement);
}
```
In SendGrid API they providing additional feature to catchup reply emails. It’s something like forwarding messages feature and SendGrid it’s known as “Inbound Parse”.
SendGrid’s Inbound Parse Webhook allows you to admit emails that get automatically broken apart by SendGrid and also transferred to a URL of your picking. SendGrid will snare the content, attachments, and the heads from any dispatch it receives for your specified hostname.
To receiving emails, you have to do couple of changes in the SendGrid settings.
We need to have following steps to complete integration with SendGrid.
•	Create a subdomain under their ‘abc.com’ domain and create new email under that. (Example: Sub domain – admin.abc.com, Email - info@ admin.abc.com)
•	Provide the newly created subdomain, email and email credentials to us to configure it in SendGrid.
•	We have to generate MX record.
•	We have to configure above MX record settings for newly created subdomain. 
•	After you configured that we can validate and complete the integration.

To add MX record you must go to Settings - Sender Authentication direction and it will display an interface regarding the Domain Authentication.

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/azure-sendgrid-domain-authentication.jpg" class="full-width-image" title="SendGrid sender verification">
        <p>Sender verification.</p>
    </div>
</div>

To receive the reply mails you have to add your API endpoint. It will received as form-data. Then you have to add the API URL to add Inbound Parse. If you want to catchup the receiving emails, you must go to Settings - Inbound Parse direction and it will display an interface regarding the Inbound Parse.

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/azure-sendgrid-inbound.png" class="full-width-image" title="SendGrid sender verification">
        <p>Sender verification.</p>
    </div>
</div>

Click on the “Add Host & URL” button. A drawer should be displayed.
•	You must select a Domain
•	Destination URL field, I’m using Ngrok to access whatever you are running on localhost:5001 through the URL that follows Forwarding above(More details to click - Product | ngrok)

First what you have to do is generate accessible URL from Ngrok. There is a command to run and command should be “ngrok http https://localhost:5001”.

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/api-test-with-ngrock.jpg" class="full-width-image" title="SendGrid sender verification">
        <p>Sender verification.</p>
    </div>
</div>

Your accessible URL should be https://ec0d-45-121-88-191.ngrok-free.app.
Then put the accessible URL with related API call and put the URL in Inbound parse.

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/azure-sendgrid-addhost-url.jpg" class="full-width-image" title="SendGrid sender verification">
        <p>Sender verification.</p>
    </div>
</div>

After the SendGrid setup you must need to create a POST method in the API controller.

``` c#
    [HttpPost("getReply")]
    public async Task<ActionResult<bool>> GetReply()
    {
        var result = Request.Form;
        return Ok(await Task.FromResult(true));
    }
```
Let’s try to send an email and get a reply message information to our endpoint.
Now I’m going to send an email.

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/postman-test.jpg" class="full-width-image" title="SendGrid sender verification">
        <p>Sender verification.</p>
    </div>
</div>

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/sendgrid-inbound-parser.png" class="full-width-image" title="SendGrid sender verification">
        <p>Sender verification.</p>
    </div>
</div>

Then, I’m adding reply for this mail.
<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/sendgrid-reply-to-message.png" class="full-width-image" title="SendGrid sender verification">
        <p>Sender verification.</p>
    </div>
</div>

In here what we are expecting is catch the replay message in our endpoint. So, the Text should be “This is the reply message!!”.

<div class="row">
    <div class="col-md-12">
        <img src="../assets/2024-09/sendgrid-received-message.png" class="full-width-image" title="SendGrid sender verification">
        <p>Sender verification.</p>
    </div>
</div>

This is the way how we can get the reply messages from the SendGrid.

Conclusion
Now we all we know the power of SendGrid mailing service within the minimum effort and how we going to use it in the real application. Furthermore, we use SendGrid to catch-up replied emails with attachments, message Id, references and etc.
