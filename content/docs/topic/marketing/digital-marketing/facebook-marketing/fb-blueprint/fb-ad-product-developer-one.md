---
title: "Facebook Certified Ad Product Developer I"
---

# Facebook Certified Ad Product Developer I

## Facebook Pixel

The Facebook pixel is a tool that helps you understand a consumer's activities on your website, and further utilize those activities on Facebook platform to measure the effectiveness of your advertising, optimize your ad delivery, and define your own targeting audience.

### Pixel Functionality

Track conversions on Facebook ads

- Pixel is triggered when someone visits your site and takes an action (e.g. buying something). This lows you to see how your campaigns are performing based on customer actions.

Optimize ads for people most likely to convert

- Deliver ads to people who are more likely to take certain actions (*conversion optimization*)

- Can also optimize for higher-value purchases to help achieve higher Return on Ad Spending through *value optimization*

Generate custom audience for better targeting/re-targeting experience

- Reach high-value customers by using *custom-audience*
- Expand it to *lookalike* audience to reach new people likely to be interested in your business

#### Pixel Benefits

Evaluate return on ad spend

- More precisely attributing online behavior to your ads

Measure cross-device conversions

- See how people me between devices when engaging with your content
- Determine on what devices they are most likely to convert

Optimize ad delivery

- Knowing how people use your website can imply what they're likely to do next
- Enable adjustments to ad delivery such as only displaying brand awareness campaigns to people who've never visited your website, or offering limited-time discount codes to people who've abandoned online shopping carts

Build effective advertising audiences

- Provides custom audiences and lookalike

Unlock additional Facebook advertising tools

- Web conversion campaigns, Custom Audiences from your website, dynamic ad delivery, and metrics, such as cost per lead or cost per conversion, are only available to advertisers who've installed pixel on their websites.


### Pixel Technical Overview

- A piece of code that registers actions that happens on your websites
- Comes with a set of preprogrammed standard events, but custom ones can be created
- Works on both mobile and desktops

Consists of two parts

- Base code: installed on all pages to provide baseline for event measuring
- Event code: Only install on specific pages where you want to measure actions or events important to business goals
  - For example , add the Add to Cart event code on the page where people would add items to their shopping cart

Data Sent

Personally Identifiable Information (PII), if any, is sent and received using data hashing, matched with anonymized Facebook data, then securely deleted.

- **HTTP headers**: IP address, browser info, page location, document, referrer, and device
- **Pixel data**: pixel ID and Facebook cookie
- **Button-click data**: buttons clicked by visitors and the labels, page visited due to the click, form-field names (form-field values need to be included as part of advanced matching/optional values)
- **Page metadata**: Page description, tags, keywords

### How Facebook Match People

A combination of computer, browser, and login data results in a hash that's stored on the Facebook side, which is associated with a person's unique Facebook ID.

When someone logs into Facebook in a browser:

- Facebook records the hash
- When your webpage is visited, Facebook servers receive the pixel call from your site
- Facebook records that visit with the hash of who visited
- Facebook can then match signature with a Facebook ID
- Facebook drop the visit record after the matching process

One Facebook ID can have multiple hashes associated. A person can match to multiple computers and browsers as long as they have logged into Facebook

### Events

**PageView** event is part of the Pixel base code and is fired on every page. This event allows you to create rules and audiences, and optimizes towards those who visited a certain page from your site using **URL rules** as filters.

You can use a set of standard events to let Facebook know how far along in the funnel the current visitor reached.

## Business Manager

### What is Facebook Business Manager

Business Manager is a free Facebook platform that helps advertisers integrates Facebook marketing with external partners. It allows you to run and track ads, manage assets (Pages and ad accounts), and add an agency or marketing partners to help manage your business

- Create manage assets (e.g. Facebook Page, Instagram accounts, audience list, product catalog) - all in one place
- Control user access and permissions for everyone who works on your ad accounts and maintain ownership of your assets
- Track your ads on Facebook and Instagram more efficiently with overviews and detailed views of spending/impression