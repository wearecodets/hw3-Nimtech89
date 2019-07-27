# 💳 Payment Form Exercise (Part 2) 

> :clock9:&nbsp; &nbsp; **Due:** Saturday, July 13 @ 9 am
>
> :mag_right:&nbsp; &nbsp; **Code Review:** Thursday, July 11 
>
> Still unclear about requesting a PR review? [See the course info](https://github.com/wearecodets/phase-two/blob/master/week-zero/about.md#homework-pull-request).

## Objective

After completing this assignment, you should have two branches: `master` and `feature-checkout`. Only one PR is needed. 

**Do not modify `index.html`, `index.js` or `.scss` files in `src/stylesheets`. Your code should only be in `src/main.js`.**

If it's your first time working on this project, run `npm install`. Otherwise, just `npm start` to begin working.

## Branching Rules

1. Never work directly on the `master` branch. 
2. `origin/master` always represents the latest code deployed to production (Netlify).
2. Create a new branch for each homework topic:
    - Prefix your branch with `feature-` to work on new features. For example, `feature-accordion`.
    - Prefix your branch with `fix-` to work on bug fixes. For example, `fix-paypal`.

## Directions

### 1. Deploy to Production 

Just like the previous homework, connect this Github repo's `master` branch to Netlify and customize the domain URL to have the same name as this homework repo – for example: `http://hw3-niko.netlify.com`. From now on, every merged PR will trigger a deployment to this URL. 
[![Netlify Status](https://api.netlify.com/api/v1/badges/07005862-85a5-49ec-800c-33a3679a5b21/deploy-status)](https://app.netlify.com/sites/hw3-nimtech89/deploys)
When you are done, [add a status badge](https://www.netlify.com/docs/continuous-deployment/#status-badges) below. Note that you may commit directly on `master` for this since it is such a tiny change.

### 2. Implement the Checkout Feature

Your fix for the unclickable Pay button last week did not make your boss happy. Instead, he wants your team to build a prototype of the checkout feature.

Since the boss is big on [UX](https://en.wikipedia.org/wiki/User_experience), your coworkers have styled a checkout flow in a separate branch called `feature-checkout`; All you need to do is `git checkout` and code the JavaScript. The checkout flow they built works like this:


1. After the pay button is clicked, a full page overlay with a loader needs to be displayed using the `modal--full` class.

2. While the loader animates, use [`setTimeout()`](https://www.w3schools.com/jsref/met_win_settimeout.asp), to simulate a slow connection of three seconds. Note that ***3 seconds = 3000 milliseonds***.

3. After the delay, toggle the `.checkout--finished` class on the `.checkout` component, removing the loader and bringing a result screen into the modal. 

    This result screen must be either a success (`.checkout--success`) or failure (`.checkout--failed`):

    - ✅ In case of success, print a thank you message with the first name of the user and a brief message:
        > Thanks, [FIRST NAME] \
        > We've received your payment. \
        > Please check your inbox for a receipt.
    - ❌ In case of failure, print a rejection message with the user's email address:
        > Payment Rejected. \
        > Your transaction could not be processed. \
        > We've sent you an email at [USER@EMAIL.COM] with the details.

    See this screen grab for visual clarification:

    ![checkout-classing](https://res.cloudinary.com/yicf/image/upload/w_500/v1561977776/Code%20The%20Web/checkout-classing.gif)

4. When the user closes the modal, remove the approprite classes. Additionally, alternate the checkout outcome between success and failure, so the next time the pay button is clicked, the opposite result will happen — *Success, Failure, Success, Failure, and so on.*

    ![checkout](https://res.cloudinary.com/yicf/image/upload/w_500/v1561977299/Code%20The%20Web/checkout.gif)
