---
title: "AI, We and Tomorrow | Exploring AI's Role in Programming and the Futur"
date: 2024-08-24
---
<head>
<title>AI, We, and Tomorrow | Exploring AI's Role in Programming and the Future</title>
<meta name="description" content="Explore the future of AI and its impact on programmers, jobs, and daily tasks. Learn how to integrate OpenAI with ChatGPT as your coding assistant in this thought-provoking experiment.">
<meta name="viewport" content="width=device-width, initial-scale=1">
<link rel="canonical" href="https://conceptwelder.com/2024/08/24/ai-we-tomorrow.html">
<meta property="og:title" content="AI, We, and Tomorrow | AI in Programming and the Future">
<meta property="og:description" content="Dive into an experiment with OpenAI's ChatGPT as a coding assistant. Understand AI's current capabilities and how it affects jobs and programming.">
<meta property="og:image" content="https://conceptwelder.com/assets/2024-08-24/ai-we-tomorrow-image.jpg">
<meta property="og:url" content="https://conceptwelder.com/2024/08/24/ai-we-tomorrow.html">
<meta property="og:type" content="article">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="AI, We, and Tomorrow | Exploring AI's Role in Programming and the Future">
<meta name="twitter:description" content="An insightful look at AI's role in programming and the job market, using ChatGPT as a coding assistant in this experimental journey.">
<meta name="twitter:image" content="https://conceptwelder.com/assets/2024-08-24/ai-we-tomorrow-image.jpg">
<meta name="robots" content="index, follow">

<style>
.container {
  border: 1px solid #dedede;
  background-color: #a39d87;
  color: #000000;
  border-radius: 5px;
  padding: 10px;
  margin: 10px 0;
  width: 100%
}
.quote {
    font-size:medium;
    font-style: italic;
    color: "blue"
}
.avator {
    font-size:large; 
    background-color:white; 
    border: 2px solid grey;
    padding:1px;
    border-radius: 50%;
}

</style>
</head>

<div class="row">
    <div class="col-md-12 header-banner">
        <img src="{{site.baseurl}}/assets/2024-08-24/ai-we-tomorrow-image.jpg" class="full-width-image" title="AI, We and Tomorrow" >
    </div>
</div>
    
# <span class="avator">🤖</span> AI, We <span class="avator">🧔</span> & Tomorrow 
<span>By Sankalpa Abeygunawardhana (Human) with assistance of AI</span>

<div class="container">
<p align="center" class="quote">
"I want AI to do my laundry and dishes so that I can do art and writing, not for AI to do my art and writing so that I can do my laundry and dishes."
</p>
<p align="center" class="quote">
<a href="https://x.com/AuthorJMac/status/1773679197631701238">Joanna Maciejewska</a>
</p>
</div>

🧔People talking about AI and its capabilities more than anything this days. AI Capabilites of Drawing pictures, Singing, film making and lots and lots. And also in other sides Humans start warring about there job future as its gradually replace by AI and AI powered robots. 
There are lots of doutes debates going all arounds. 

I wanted to find out where AI is in day today activites of my job. 

As a programmrs one of the usuall task is application which is developing integration with different other platforms.

So I wanted to try integreate and see OpenAI platform using only get help from ChatGPT. Which popular virtual assistant tool of OpenAI and I think it should be the best tool get assistant when integrating OpenAI.

 In this experiment I try to act as much as not a 'Senior programmer' and try to get resolve all the issues and questions I have only using 'ChatGPT' as assuming it as a 'Human Senior Programmer'. 

# OpenAI and Nextjs
🧔In this experiment, I aim to build a small web app for programmers, allowing them to input their code and generate documentation using OpenAI's capabilities. 

## Getting Started
<p align="right" class="container">
<span class="avator">🧔</span> Hi
</p>
<p align="left" class="container">
<span class="avator">🤖</span> Hi there! How's it going?
</p>
<p align="right" class="container"><span class="avator">🧔</span>
not bad</p>
<p align="left" class="container"><span class="avator">🤖</span>
Glad to hear that! Anything on your mind today?</p>
<p align="right" class="container"><span class="avator">🧔</span>
I want to create NextJs app with OpenAI integration, Could you help?</p>
<p align="left" class="container"><span class="avator">🤖</span>
Absolutely! I can help you with that. Do you have a specific feature in mind for the app, or are you looking for a general setup guide to integrate OpenAI into a Next.js project?</p>
<p align="right" class="container"><span class="avator">🧔</span>
Yes, App should have a text area which users can enter any type script or javascript code, using  OpenAI app should generate the documentation</p>
<p align="left" class="container">
<span class="avator">🤖</span>
That sounds like a great project! Here's a step-by-step guide to help you create a Next.js app that takes TypeScript or JavaScript code input from a user and generates documentation using OpenAI's API:
</p>

## Solution provided 
🧔ChatGPT provided a 6-step guide to achieve this, with a 7th step as an enhancement.

### 1. Set Up Your Next.js App🤖
```bash
npx create-next-app@latest my-nextjs-app
cd my-nextjs-app
```
🧔Creted NextJs App with following parameter.
```bash
PS D:\Sankalpa\Personal\blog\NextJs-Solr> npx create-next-app nextjs-solr
√ Would you like to use TypeScript? ... No / Yes
√ Would you like to use ESLint? ... No / Yes
√ Would you like to use Tailwind CSS? ... No / Yes
√ Would you like to use `src/` directory? ... No / Yes
√ Would you like to use App Router? (recommended) ... No / Yes
√ Would you like to customize the default import alias (@/*)? ... No / Yes
Creating a new Next.js app in D:\Sankalpa\Personal\blog\NextJs-Solr\nextjs-solr.
```

### 2. Install Dependencies🤖
```bash
npm install openai
```
```bash
npx typescript --init
npm install --save-dev @types/react @types/node
```
### 3. Create a `.env.local` File🤖
```bash
NEXT_PUBLIC_OPENAI_API_KEY=your_openai_api_key_here
```
### 4. Build the Frontend🤖
```js
// pages/index.js or index.tsx

import { useState } from 'react';

export default function Home() {
  const [code, setCode] = useState('');
  const [documentation, setDocumentation] = useState('');

  const handleGenerateDoc = async () => {
    const response = await fetch('/api/generate-doc', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify({ code }),
    });

    const data = await response.json();
    setDocumentation(data.documentation);
  };

  return (
    <div style={{ padding: '2rem' }}>
      <h1>Code Documentation Generator</h1>
      <textarea
        value={code}
        onChange={(e) => setCode(e.target.value)}
        placeholder="Enter your TypeScript or JavaScript code here..."
        rows={10}
        style={{ width: '100%', padding: '1rem' }}
      />
      <button onClick={handleGenerateDoc} style={{ marginTop: '1rem', padding: '1rem' }}>
        Generate Documentation
      </button>
      {documentation && (
        <div style={{ marginTop: '2rem' }}>
          <h2>Generated Documentation</h2>
          <pre style={{ backgroundColor: '#f4f4f4', padding: '1rem' }}>
            {documentation}
          </pre>
        </div>
      )}
    </div>
  );
}
```
### 5. Create the API Route🤖
```js
//pages/api/generate-doc.js or generate-doc.ts:
import { Configuration, OpenAIApi } from 'openai';

const configuration = new Configuration({
  apiKey: process.env.NEXT_PUBLIC_OPENAI_API_KEY,
});
const openai = new OpenAIApi(configuration);

export default async function handler(req, res) {
  const { code } = req.body;

  try {
    const response = await openai.createCompletion({
      model: 'text-davinci-003', // or any other model suitable for code tasks
      prompt: `Generate documentation for the following code:\n\n${code}`,
      max_tokens: 150,
    });

    const documentation = response.data.choices[0].text.trim();
    res.status(200).json({ documentation });
  } catch (error) {
    res.status(500).json({ error: 'Failed to generate documentation' });
  }
}

```
### 6. Run the App🤖
```bash
npm run dev
```

## Errors and Responses.
🧔After creating the app using the steps above, I encountered some errors. Here's how I resolved them with the help of ChatGPT.

### Error #1: Human mistake. 
🧔As humans, we are prone to making mistakes, and errors can occur at any time. For instance, I tested an error by purposely creating `pages/index.js` under `/app/src/pages/index.js`. When setting up the Next.js solution, I chose to create it with the `src` folder.

Here’s how I tried to resolve that issue with the help of ChatGPT: 
<p align="right" class="container"><span class="avator">🧔</span>
When I try to access the page which I created in step 4 its return '404 This page could not be found' error
</p>
<p align="left" class="container"><span class="avator">🤖</span>
The "404 This page could not be found" error typically occurs if the page file isn't located correctly or there's an issue with the routing. Let's troubleshoot this:
</p>

🧔And provided six troubleshooting points to check.

🤖
1. Check the File Location
2. File Name
3. Restart the Dev Server
4. Clear the Cache
5. Check the Console
6. Check the Link


🧔I know that 'Check the File Location' is part of the answer, but I needed to get that directly from ChatGPT. So, I asked the following question again. 

<p align="right" class="container"><span class="avator">🧔</span>
I created next app with 'src' folder is that the issue?
</p>
🧔However, I’m unsure if I provided too much information to ChatGPT 🙂 in this question.
<p align="left" class="container"><span class="avator">🤖</span>
Yes, having a src directory can change where Next.js looks for your pages. By default, if you create a src folder, Next.js will expect your pages directory to be inside the src folder.
</p>

🧔Provided troubleshooting points to check.

🤖
1. Ensure the Structure is Correct
2. Move the pages Folder Inside src
3. Access the Page


🧔I corrected the structure, but the errors continue. 

### Error #2: Package version error
🧔This time, a package compatibility issue occurred. Following the instructions, I installed the latest version (openai@4.56.0), but the generated code snippet was not compatible with the latest library.

<p align="right" class="container"><span class="avator">🧔</span>
in step 5 I am getting following error
Module '"openai"' has no exported member 'Configuration'. Did you mean to use 'import Configuration from "openai"' instead?
</p>
<p align="left" class="container"><span class="avator">🤖</span>
It looks like the error is due to how the OpenAI package is being imported. The issue might arise from a discrepancy in the package's version or its TypeScript definitions. Let's address this by making sure the import statement is correct.
</p>

🤖
1. Check the OpenAI Package Version
2. Adjust the Import Statement
3. Ensure Correct TypeScript Usage
4. Restart Your Development Server

🧔None of the above options resolved the issue.And I checked again with ChatGPT.
<p align="right" class="container"><span class="avator">🧔</span>
I am using openai@4.56.0 version, which is latest, and non of the above resolve my issue
</p>
<p align="left" class="container"><span class="avator">🤖</span>
It seems the latest version of the OpenAI library (openai@4.56.0) has some changes in how the classes are exported. Let's address this with the correct import pattern for this version.
</p>

🤖
1. Importing the OpenAI API
2. Making API Calls

```js
import OpenAI from 'openai';

const openai = new OpenAI({
  apiKey: process.env.NEXT_PUBLIC_OPENAI_API_KEY,
});

export default async function handler(req, res) {
  const { code } = req.body;

  try {
    const response = await openai.chat.completions.create({
      model: 'gpt-4', // or the model you intend to use
      messages: [
        {
          role: 'system',
          content: 'Generate documentation for the following code:',
        },
        {
          role: 'user',
          content: code,
        },
      ],
    });

    const documentation = response.choices[0].message.content.trim();
    res.status(200).json({ documentation });
  } catch (error) {
    console.error(error);
    res.status(500).json({ error: 'Failed to generate documentation' });
  }
}
```
🧔I used TypeScript, but the provided solution was in JavaScript.
<p align="right" class="container"><span class="avator">🧔</span>
I am using TS, 
</p>
<p align="left" class="container"><span class="avator">🤖</span>
Given that you're using TypeScript with the latest OpenAI package (openai@4.56.0), here’s how to properly set up and use the OpenAI API with TypeScript:
</p>

🤖
 1. Install OpenAI and TypeScript Types
 2. Importing OpenAI in TypeScript
   
```typescript
import OpenAI from 'openai';

const openai = new OpenAI({
  apiKey: process.env.NEXT_PUBLIC_OPENAI_API_KEY,
});

import { NextApiRequest, NextApiResponse } from 'next';

export default async function handler(req: NextApiRequest, res: NextApiResponse) {
  const { code } = req.body;

  try {
    const response = await openai.chat.completions.create({
      model: 'gpt-4', // Specify the model you want to use
      messages: [
        { role: 'system', content: 'Generate documentation for the following code:' },
        { role: 'user', content: code },
      ],
    });

    const documentation = response.choices[0].message.content.trim();
    res.status(200).json({ documentation });
  } catch (error) {
    console.error(error);
    res.status(500).json({ error: 'Failed to generate documentation' });
  }
}
```
 3. TypeScript Configuration
 4. Running the Server

🧔I'm still encountering an optional chaining error.

<p align="right" class="container"><span class="avator">🧔</span>
now its complain about 'const documentation = response.choices[0].message.content.trim();' line 'Object is possibly 'null'.ts'
</p>
<p align="left" class="container"><span class="avator">🤖</span>
The TypeScript error 'Object is possibly 'null' is a common issue when dealing with optional properties or API responses that might not always return the expected structure. To handle this safely, you should check if the object exists and handle the null or undefined case appropriately. 
</p>

Safely Accessing response.choices[0].message.content

<p align="right" class="container"><span class="avator">🧔</span>
ok, with that its resolve
</p>
<p align="left" class="container"><span class="avator">🤖</span>
Great to hear that resolved the issue! If you have any more questions or need further assistance with your project, feel free to ask.
</p>

🧔I finally got a working solution, but it still has some runtime errors 


## Final solution and runtime errors.

<p align="right" class="container"><span class="avator">🧔</span>
now when I try to generate document for a simple type script program, its return '
       POST http://localhost:3000/api/generate-doc 500 (Internal Server Error)'
</p>
<p align="left" class="container"><span class="avator">🤖</span>
A 500 Internal Server Error generally indicates something went wrong on the server side. Let's troubleshoot this step-by-step:
</p>

  🤖
   1. Check the Error Message
   2. Verify API Key
   3. Check for Request Payload
   4. Validate OpenAI Request
   5. Test with Simplified Input
  
🧔 Beyond this point, the remaining errors were due to my free subscription. I’ve chosen not to list them all here to avoid making this article unnecessarily lengthy.

[Review the full conversation here.](https://chatgpt.com/share/7c8523c0-66de-4e06-b9ab-ee213e629ddf)

## With Other AI Platforms
🧔 I tried the same scenario on two other popular platforms but couldn’t get very far. 

### Claude and Nextjs
Experimental integration with [Claude](https://claude.ai/) and Next.js had to stop due to a runtime Cross-Origin issue. 



### Gemini and Nextjs
I couldn’t continue the integration with the [Google Gemini](https://gemini.google.com/) platform because the provided NPM package was not available in the NPM registry. 

[Review the full conversation here.](https://g.co/gemini/share/2ceeff1e786d)

# Tomorrow
I believe that if I had provided more details to the AI, I might have received better outputs in some of the scenarios above, such as explaining how I created the Next.js app. 

Additionally, I think that understanding own libraries and related issues is a matter of time for the AI.

In conclusion, I believe...

#### Yesterday
We developed the code based on the business requirements using only human effort.


#### Today
We are coding based on business requirements with the assistance of AI. 

#### Tomorrow
AI will code based on the business requirements, with human assistance.

