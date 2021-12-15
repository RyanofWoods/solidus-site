---
title: Introducing Solidus PayPal Marketplace
date: 2021-12-15
tags: Solidus, Paypal, Extension
author: Ryan Woods
cover_image: /blog/2021/12/15/introducing-solidus-paypal-marketplace/cover.jpg
description: >
  All about Solidus PayPal Marketplace
---

We're excited to announce that Solidus has a new official extension - Solidus PayPal Marketplace! This extension allows seller users to join the platform and sell their own products.
On top of this, it will be easy to setup PayPal, as we connected it thanks to our [Solidus PayPal Commerce extension!](https://github.com/solidusio-contrib/solidus_paypal_commerce_platform).

A special thanks to _PayPal Commerce Platform for Marketplaces and Platforms_ for supporting Solidus and allow us to create this for you!

After this guide, you'll know how to create a new eCommerce marketplace platform, similar to Etsy, eBay, Amazon.

Exciting!

### Basic concept:
Your Solidus Store will have 3 types of users:
- the Platform/Marketplace Owner;
- Sellers; and
- Buyers

#### Marketplace Owner
To be the marketplace owner, you'll need a PayPal business account.

They manage all the listed products and can set:
- possible shipping methods; and
- products' categories and images.

As the marketplace owner, you'll be responsible to contact the Buyer when an order's shipment/line item is rejected.

You'll also be able to set a percentage on each seller to take their payments as a fee.

### Sellers
Are able to:
- list items with its price available quantity;
- manage their orders
  - cancel/accept contained items
  - change an item's quantity (in rare scenarios where the seller does not have enough quantity)
  - mark the shipment as shipped
  - add a shipping tracking URL if available

They cannot:
- Control possible shipping methods and their products' categories and images.

However, Solidus is very customizable.

### Buyers
As of right now, they can only buy products from one seller at a time, similar to Etsy.

### Features
#### PayPal Payments
It will take care of capturing payments and disburse money to the seller and keep the fee for the marketplace platform.
The payment will be captured only when the sellers mark the shipment as shipped.

#### CSV Uploader
The seller is able to list products as well as update their available quantities by uploading a CSV.
The CSB should have 3 columns for the products: SKU, price and availability quantity.

Note, when the seller wants add more stock quantity on their product, then the availability column should be the new inventory quantity and not how much it will be in total afterwards.

### More information
This extension has all the stable necessary functionality, and Solidus allows you to customize it massively. So go make an awesome store!

### Installation and Requirements
[Go here](https://github.com/solidusio-contrib/solidus_paypal_marketplace#installation).

### Marketplace Owner Onboarding
Seller onboarding:
1) Platform Owner creates the Spree::Seller
2) Platform Owner creates the Spree::User
3) Platform Owner should be able to link any user to the desired Seller
4) From the seller edit page, he/she can click the button `start onboarding process`
5) The platform generates the PayPal signup link.
https://developer.paypal.com/docs/limited-release/commerce-platform/v2/seller-onboarding/before-payment/#2-generate-a-paypal-sign-up-link
We can add the partner_config_override fields with the platform information and a predefined endpoint where the seller will be redirected at the end of the onboarding process(step 6)
6) Store the action_url on the Spree::Seller entity
7) Invite the Seller to login with user and password by email specified on Spree.user_class.
8) When the Seller has signed in to the platform, it shows a button that links the action_url to start the onboarding process.
9) The link will open a PayPal onboarding popup
10) When the process is done the user is redirected back to the platform. The Platform should receive an URL like:
11) Store the above information received as GET to the Seller and update the Seller status to accepted or rejected.
12) Redirect the Seller to the dashboard page













1. Seller starts their onboarding process
2. They login in to their paypal account

After being approved by PayPal, the seller will be able to see the "seller dashboard".


SEO NOTES:
create website where people can list/sell items
marketplace
paypal
solidus
ecommerce
buyers
sellers




Offers are the prices created by the seller
