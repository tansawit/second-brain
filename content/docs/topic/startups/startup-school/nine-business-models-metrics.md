---
title: Nine Business Models and the Metrics Investors Want
bookToC: 3
---

# Nine Business Models and the Metrics Investors Want

*Notes from Anu Hariharan's talk as part of Y Combinator’s Startup School 2019 Series.*

Original Video: [here](https://youtu.be/PTg3RZPXgLg)

## Thinking about which metrics to track

Find out which business model you fit in, not your industry. (How you plan to charge your users)

Nine 'verticals':

{{<columns>}}

- Enterprise
- Subscription
- E-Commerce
- SaaS
- Transactional

<--->

- Advertising
- Usage-based
- Marketplace
- Hardware

{{</columns>}}

## Common Mistakes

| Mistakes                  | Solution                       |
| ------------------------- | ------------------------------ |
| Cumulative Charts         | Monthly Data                   |
| Not labelling Y-Axis      | Label with the right detail    |
| Changing the Y-Axis Scale | X and Y axes intersect at zero |
| Showing only % gains      | Show absolute number and %     |


## Industries

### Enterprise

Company that sells services or software to other businesses on a single-license basis. (fixed terms, designated contract values, renewal at end of term)

Examples: 

- [Docker](https://www.docker.com/)
- [Cloudera](https://www.cloudera.com/)
- [FireEye](https://www.fireeye.com/)

| Metrics         | Note                                               |
| --------------- | -------------------------------------------------- |
| Bookings        | Sum of value of all customer contract              |
| Total Customers | Total number of unique customer contracted (today) |
| Revenue         | Recognized when service is provided                |


### SaaS

A software-as-a-service company sells subscription-based licenses for a cloud-hosted software solution.

Examples

- [IronClad](https://ironcladapp.com/)
- [Segment](https://segment.com/)
- [Sendbird](https://sendbird.com/)

| Metrics                         | Note                                                                                                                                                                      |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| MRR (Monthly Recurring Revenue) | Revenue rendered in a given month (does not recognize non-recurring fees)                                                                                                 |
| ARR (Annual Recurring Revenue)  | Revenue components that are recurring on an annual basis                                                                                                                  |
| Gross MRR Churn                 | MRR lost in a given month / MRR at the beginning of the month                                                                                                             |
| Paid CAC                        | Cost per customer acquired through paid marketing channels (total sales and marketing spend in given month / total customers acquired via paid channels in a given month) |

### Subscription

A Company that sells a product or service on a recurring basis

Examples

- [The Athletic](https://theathletic.com/)
- [Dollar Shave Club](https://www.dollarshaveclub.com/)
- [Blue Apron](https://www.blueapron.com/)

| Metrics                                 | Note                                                                                                                                                                      |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| MRR (Monthly Recurring Revenue)         | Revenue rendered in a given month (does not recognize non-recurring fees)                                                                                                 |
| MRR CMGR (Compound Monthly Growth Rate) | Implied compounded monthly MRR growth rate between two disparate months [CMGR=(last month MRR/first month MRR)^(1/num_months)-1]                                          |
| Gross User Churn                        | Total customer lost in a given period/prior period total customers                                                                                                        |
| Paid CAC                                | Cost per customer acquired through paid marketing channels (total sales and marketing spend in given month / total customers acquired via paid channels in a given month) |

### Transactional

A company that enables a financial transaction on behalf of a customer and collects a fee.

Examples

- [Stripe](https://stripe.com/)
- [PayPal](https://www.paypal.com/)
- [Coinbase](https://www.coinbase.com/)
- [Brex](https://brex.com/)

| Metrics                    | Note                                                                                                                                                                      |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Gross Transactional Volume | Total sales or payment dollar volume transacted in a given period                                                                                                         |
| Net Revenue                | The portion of GTV that the company recognizes as revenue for service rendered                                                                                            |
| User Retention             | Percent of customers who go on to make at least one purchase in month 2 (cohort metric => recalculated to include each new cohort acquired)                               |
| Paid CAC                   | Cost per customer acquired through paid marketing channels (total sales and marketing spend in given month / total customers acquired via paid channels in a given month) |


### Marketplace

A company that acts as an intermediary in the sales of good or service between sellers and buyers

Examples

- [AirBnB](https://www.airbnb.com/)
- [eBay]((https://www.ebay.com/))

| Metrics                                         | Note                                                                                                                                                                      |
| ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| GMV (Gross Merchandise Value)                   | Total sales dollar volume of merchandise transacted in a given period                                                                                                     |
| Net Revenue                                     | The potion of GMV that the company recognizes as revenue for service rendered                                                                                             |
| Net Revenue CMGR (Compound Monthly Growth Rate) | Implied compounded monthly net revenue growth rate between two disparate month [CMGR=(last month MRR/first month MRR)^(1/num_months)-1]                                   |
| User Retention                                  | Percent of customers who go on to make at least one purchase in month 2 (cohort metric => recalculated to include each new cohort acquired)                               |
| Paid CAC                                        | Cost per customer acquired through paid marketing channels (total sales and marketing spend in given month / total customers acquired via paid channels in a given month) |

### E-Commerce

A company that sells physical good online. Generally these companies manufacture and inventory those goods.

Examples

- [Warby Parker](https://www.warbyparker.com/)
- [Bonobos](https://bonobos.com/)
- [Memebox](https://us.memebox.com/)

| Metrics         | Note                                                                                                                                                                      |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Monthly Revenue | Total Revenue in a given month                                                                                                                                            |
| Revenue CMGR    | Implied compounded monthly revenue growth rate between two disparate month [CMGR=(last month MRR/first month MRR)^(1/num_months)-1]                                       |
| Gross Margin    | Gross profit in a given month / total revenue in the same month (gross profit = total revenue less cost of sales and COGS (cost-of-goods-sold))                           |
| Paid CAC        | Cost per customer acquired through paid marketing channels (total sales and marketing spend in given month / total customers acquired via paid channels in a given month) |

### Advertising

A company that offers a free service to customers and derives revenue predominantly/entirely from advertisers.

Examples:

- [Snapchat](https://www.snapchat.com/)
- [Twitter](https://www.twitter.com/)
- [Reddit](https://www.reddit.com/)

| Metrics                    | Note                                                                                                     |
| -------------------------- | -------------------------------------------------------------------------------------------------------- |
| DAU (Daily Active Users)   | Total number of unique users active in a 24-hour day, averaged over a given period of time               |
| MAU (Monthly Active Users) | Total number of unique users active at least once in last 28 days                                        |
| Percent Logged-In          | Total monthly active users with a registered account / total unique visitors over the same 28-day window |

### Hardware

A company that sells physical devices to consumers or businesses

Examples:

- FitBit
- GoPro
- Xiaomi

| Metrics         | Note                                                                                                                                                                      |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Monthly Revenue | Total Revenue in a given month                                                                                                                                            |
| Revenue CMGR    | Implied compounded monthly revenue growth rate between two disparate month [CMGR=(last month MRR/first month MRR)^(1/num_months)-1]                                       |
| Gross Margin    | Gross profit in a given month / total revenue in the same month (gross profit = total revenue less cost of sales and COGS (cost-of-goods-sold))                           |
| Paid CAC        | Cost per customer acquired through paid marketing channels (total sales and marketing spend in given month / total customers acquired via paid channels in a given month) |