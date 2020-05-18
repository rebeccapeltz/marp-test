---
marp: true
title: Marp CLI example
description: Hosting Marp slide deck on the web
theme: cl-theme
paginate: true
_paginate: false
# header: 'Header content'
footer: 'Advanced Concepts for Developers'

---

# Create a free account

You can create a new, free account on Cloudinary by adding `+training` to your
email when registering.  

Signup [here](https://cloudinary.com/users/register/free)

For example, I can create an account with this email:
rebecca.peltz+training@cloudinary.com.  

This is important, as we’ll be configuring settings and using Cloudinary add-ons.

---
# Upload

If you are using this module out of sequence, you'll need to upload assets for the exercise.  The video upload will upload 4 short videos used in the **video-player** module,  and the image upload uploads the files used in the **underlay-overlay** module.

## Upload Video

```bash
node video-player/upload-video-collection.js
```

### Upload Images

```bash
node overlay-underlay/upload-images.js
```
---

# Node/NPM

We’ll be coding in Node.js (v > 10.x), as well as creating some
HTML/JavaScript/CSS files.

Install the latest version of node/npm to follow along with node exercises.
[Download node.js and npm](https://nodejs.org/en/download/)  
 

You can update node/npm with this command: `npm i npm@latest -g`  

![node version](https://res.cloudinary.com/cloudinary-training/image/upload/v1588283690/book/setup-node-version.png)

---

---

# IDE Visual Studio Code  

I’ll be using [Visual Studio Code](https://code.visualstudio.com/) with the [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) to serve html files on localhost.  

Another alternative to using the VS Code live server extension is to `npm i -g http-server` and open the server from the terminal with `npx http-server`.

---


# Course Code Repository

The code repo is [here](https://github.com/cloudinary-training/advanced-concepts) 

The easiest way to work with this repo is to download it. Most of the work will involve running local node.js scripts or serving from localhost.

This repo contains code and assets used during the exercises.  You'll find assets under the `assets` and `secure-assets` directories.  *The files can be served from `github.io`. This is useful when we’re working on modules like auto-upload/fetch. For example: 
https://cloudinary-training.github.io/advanced-concepts/assets/images/cc0.png 

**(Optional)** If you want to serve your account repo on github.io, I recommend forking or duplicating this repository into your own GitHub account. Forking allows you to pull from upstream later if you want. Go to Settings and set up [gh pages](https://help.github.com/en/github/working-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) to serve the html files.  

---

# Environment Variables
Your `.env` file is `.gitignored `and can’t be accidentally checked into a repository
because it will contain your `API_SECRET`.   

In the root of the project, you’ll find a `.env.template` file.
Copy it to an `.env` file and add your information: 
```bash
cp .env.template .env
```
This link will take you to the Console, where you can copy the Cloudinary 
URL into your buffer: https://www.cloudinary.com.

The .env file should contain the CLOUDINARY_URL and a USER_NAME which is the email you used to sign up for the account.

```bash
CLOUDINARY_URL=<cloudinary URL from console>
USER_NAME=<cloudinary account email>
```
---
# How to Run the node.js scripts 
See the .env.template for example of what is needed as described above.  Before running any scripts you need to run `npm install` in the terminal in the directory containing the package.json.  

You may want to run npm install in all the subdirectories prior to starting the
course. This can guarantee you are ready if you are accessing the course in a
network where npm install may be blocked.
These are the directories that contain a package.json and need the npm install:

1. signing-widgets/bonus  
2. signing-widgets/server  
3. user-upload-workflows/remote-functions  
4. video-player/vuejs  

All scripts (unless otherwise noted in a module) can be run from the root of the
project in the terminal.  

---
# How to Run a Script

If I want to run a script in the /access-control directory to upload a private asset, I
can run it from the terminal like this from the root directory:
```bash
node access-control/private/upload-private.js
```
---
# Test your setup

Test that your environment variables are setup correctly:

```bash
node test-env.js
```

Test that you can upload assets:

```bash
node test-update.js
``` 

---



### Created by Yuki Hattori ([@yhatt](https://github.com/yhatt))

https://github.com/yhatt/marp-cli-example