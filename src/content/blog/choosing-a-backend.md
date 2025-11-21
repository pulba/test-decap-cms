---
layout: blog
title: Choosing a Backend
date: 2025-11-21T20:45:00.000+07:00
thumbnail: /assets/img_2344.jpg
rating: 3
---



Now that you have your Decap CMS files in place and configured, all that’s left is to enable authentication.

To follow this guide, you need a [Netlify](https://app.netlify.com/) account. If you don’t have one, you can [sign up for free](https://app.netlify.com/signup).

You can learn about other authentication options in the [Backends](https://decapcms.org/docs/backends-overview) doc.

## Setup on Netlify

Netlify offers a built-in authentication service called [Identity](https://docs.netlify.com/security/secure-access-to-sites/identity/). In order to use it, connect your site repo with Netlify. Netlify has published a general [Step-by-Step Guide](https://www.netlify.com/blog/2016/10/27/a-step-by-step-guide-deploying-a-static-site-or-single-page-app/) for this, along with detailed guides for many popular static site generators.

If you will use Netlify only for authentication, you can skip the above mentioned deployment step.

### Enable Identity and Git Gateway

Netlify’s Identity and Git Gateway services allow you to manage CMS admin users for your site without requiring them to have an account with your Git host or commit access on your repo. From your site dashboard on Netlify:

1. Go to 

   **Integrations > Identity > Netlify Identity - Enable**

   , click 

   **Enable Identity**

   , and go to 

   **Configuration and usage**

   .
2. Under 

   **Registration**

   , select 

   **Open**

    or 

   **Invite only**

   . In most cases, you want only invited users to access your CMS, but if you’re just experimenting, you can leave it open for convenience.
3. If you’d like to allow one-click login with services like Google and GitHub, check the boxes next to the services you’d like to use, under 

   **External providers**

   .
4. Scroll down to 

   **Services > Git Gateway**

   , and click 

   **Enable Git Gateway**

   . This authenticates with your Git host and generates an API access token. In this case, we’re leaving the 

   **Roles**

    field blank, which means any logged in user may access the CMS. For information on changing this, check the 

   [Netlify Identity documentation](https://www.netlify.com/docs/identity/)

   .

## Add the Netlify Identity Widget

With the backend configured to handle authentication, now you need a frontend interface to connect to it. The open source Netlify Identity Widget is a drop-in widget made for just this purpose. To include the widget in your site, add the following script tag in one or two places, depending on the method you choose for user registration:
