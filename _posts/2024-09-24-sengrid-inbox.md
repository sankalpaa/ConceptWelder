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



    //TO ADD
}
```
