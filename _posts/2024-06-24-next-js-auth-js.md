<div class="row">
    <div class="col-md-12 header-banner">
        <img src="{{site.baseurl}}/assets/2024-06-24/header.jpg" title="OAuth in Next.js Using Auth.js" >
    </div>
</div>
    
# OAuth in Next.js Using Auth.js

When you need to register on a new platform, what’s your preferred way? Do you fill out a lengthy form, validate your email, create a strong password, and then manage that password? Or do you simply log in using your social media account or another [OAuth](https://oauth.net/2/) provider? Most likely, you opt for the convenience of an OAuth provider. But how do you implement this in a Next.js application? Follow this step-by-step guide to seamlessly integrate OAuth with [Next js](https://nextjs.org/) using [Auth.js](https://authjs.dev/).

## 1. Let's start with new Next.js App
 I used [Create Next App](https://www.npmjs.com/package/create-next-app) CLI tool.

 ```bash
 npx create-next-app@latest
 # with 
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```
<div class="row">
    <div class="col-md-12">
        <img src="{{site.baseurl}}/assets/2024-06-24/next-js-basic-app.PNG" title="Basic Next.js app running">
        <p>Basic Next.js app running.</p>
        <span>
        <a href="https://github.com/sankalpaa/NextJs-AuthJs/tree/327446e0c0659859467088aa9bb7d7021cf7d8c8">Step 1 source</a>
        </span>
    </div>
</div>

## 2. Install and setup Auth.js
Although it's still in beta, that's okay! After installing the npm package, you'll need to generate an auth secret and configure it in the `.env` file

 ```bash
 # to install pacakge
npm install next-auth@beta

# go generate auth secreat key
npx auth secret
```

<div class="row">
    <div class="col-md-12">
        <span>
        <a href="https://github.com/sankalpaa/NextJs-AuthJs/tree/69abc5c02bcefa17b1bad68f3f8740d0c3326dc4">Step 2 source</a>
        </span>
    </div>
</div>

## 3. Setup Auth configuration file and API files.
You'll need to create two files to hold configuration information and handle the API. Respectively, create the `auth.ts` file for configuration and the `api/auth/[...nextauth]/route.ts` file for the API. 

 ```bash
 # auth.ts
import NextAuth from "next-auth"
 
export const { handlers, signIn, signOut, auth } = NextAuth({
  providers: [],
})
```
 ```bash
 # route.ts
import { handlers } from "@/configuration/auth";

export const { GET, POST } = handlers
```

We can verify the behavior by browsing to the API method. For example, we can test the 'Signin' API method directly in the browser.


 ```bash
http://localhost:3000/api/auth/signin
```

<div class="row">
    <div class="col-md-12">
        <img src="{{site.baseurl}}/assets/2024-06-24/next-js-auth-js-signin-api-without-providers.PNG" title="Auth.js Signin method">
        <p>Auth.js Signin method (no providers listing).</p>
        <span>
        <a href="https://github.com/sankalpaa/NextJs-AuthJs/tree/427745f3da8eef46489c35bb44970096f81d5962">Step 3 source</a>
        </span>
    </div>
</div>

Yes, No providers listing. We'll list them up in a minute.

## 4. Setup required providers. 
Yes, it's easy—just import the required providers and configure them. Always remember to set up your app with your provider and add the `CLIENT_ID` and `CLIENT_SECRET` values in the `.env` file.

If you want to get started quickly, here's how to set it up with GitHub.
https://authjs.dev/guides/configuring-github

The OAuth providers supported by Auth.js are listed [here](https://authjs.dev/getting-started/authentication/oauth).

 ```bash
 # auth.ts
import NextAuth from "next-auth"
import Github from "next-auth/providers/github"
import Google from "next-auth/providers/google"
import Facebook from "next-auth/providers/facebook"
 
export const { handlers, signIn, signOut, auth } = NextAuth({
  providers: [Github, Google, Facebook],
})
```

<div class="row">
    <div class="col-md-12">
        <img src="{{site.baseurl}}/assets/2024-06-24/next-js-auth-js-signin-api-with-providers.PNG" title="Auth.js signin with few providers">
        <p>Auth.js Signin method with few providers.</p>
        <span>
        <a href="https://github.com/sankalpaa/NextJs-AuthJs/tree/cc6575dc96d5ac1abe81fd0c7119255a02ee7e93">Step 4 source</a>
        </span>
    </div>
</div>

## 5. Session Management. 

You can use `session.user` to validate if there is a valid user after logging in with an OAuth provider.

```bash
# user-avator.tsx
import { auth } from "@/configuration/auth"
export default async function UserAvatar() {
    const session = await auth()

    if (!session?.user) return null

    return (
        <div>
            {
                session.user.image && (
                    <img src={session.user.image} className="avator-image" alt="User Avatar" />
                )
            }
            <h5><a href="/pages/profile">{session.user.name}</a></h5>
        </div>
    )
}
```
Sign-in helper component.
```bash
# Sign-in.tsx 
import { signIn } from "@/configuration/auth"

export default function SignIn() {
  return (
    <form
      action={async () => {
        "use server"
        await signIn()
      }}
    >
      <button className="btn btn-blue" type="submit">Signin</button>
    </form>
  )
} 
```

<div class="row">
    <div class="col-md-12">
        <div class="row">
            <div class="col-md-6">
                <img src="{{site.baseurl}}/assets/2024-06-24/next-js-auth-js-user-avator.PNG" title="Auth.js user avator using session">
            </div>
            <div class="col-md-6">
                <img src="{{site.baseurl}}/assets/2024-06-24/next-js-auth-js-sign-in-component.PNG" title="Auth.js signin">
            </div>
        </div>
        <p>Auth.js user avator with session and sign-in.</p>
        <span>
        <a href="https://github.com/sankalpaa/NextJs-AuthJs/commit/c0becf46541cc8b707baaa14a687e753a3631579">Step 5 source</a>
        </span>
    </div>
</div>

New Sign out component in `pages\profile\page.tsx`
<a href="https://github.com/sankalpaa/NextJs-AuthJs/commit/ccb0a0a104506e42e0d6d3c1beb31c92285dd0c2">Step 5 source with sign out</a>

## 6. Middleware base Route protection
All protected content routes are secured using a middleware-based route guard (`middleware.ts`). Protected pages are configured within the same file. In the following middleware, users are redirected to the `/pages/login` route if they try to access a protected route without a valid user session.


```bash
#middleware.ts
import { auth } from "./configuration/auth"

#routes should protected
export const config = {
  matcher: ['/pages/profile', '/pages/protectedPage1'],
}

export default auth((req) => {
  if (!req.auth) {
    const newUrl = new URL("/pages/login", req.nextUrl.origin)
    return Response.redirect(newUrl)
  }
})
```

<a href="https://github.com/sankalpaa/NextJs-AuthJs/commit/ccb0a0a104506e42e0d6d3c1beb31c92285dd0c2">Step 6 source</a>

[Check complete github repo](https://github.com/sankalpaa/NextJs-AuthJs)

I hope this helps, and I look forward to seeing you build your next tool with OAuth. Thank you!

