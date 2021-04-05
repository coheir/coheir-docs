# Point Of Sales system

One possible entry point to the booking system, is via staff members booking for customers that show up in person, instead of booking via the website. Doing this can also involve buying other items sold at the same physical position. This in turn leaves us with a need to either develop POS as part of the booking system, or deeply integrate with an already existing solution. We chose the latter, and are here describing what those needs are more specifically.

## Primary user flows

Where our POS needs might be different that just having a POS for a kiosk or something like that, we have described these user flows here, together with an idea on how we envision this to be solved. If a POS vendor has other ways to solve the same scenarios, we are all ears.

### Paying parked bookings

If a person shows up with a booking that has not been payed, or goes through a booking right there, plus have physical wares to buy as well, we want to limit the risk of withdrawing wrong amounts, so both the booking and the physical wares can be paid together in one go in POS.

We expect that to happen by adding parked orders in the POS to the current transaction and pay for everything in one go. This potentially also includes the need for a callback to our booking system, that the parked booking has now been payed. Being able to do so would definitely be a plus.

### Putting it on the tab

Especially for campers, there will be a need for just adding expenses to their existing tab, that will be tallied up by the end of their stay. Therefore, some kind of integrated search will be needed as well, so we can look up a customer in the booking system, directly from the POS to reduce the risk of adding expenses to the wrong camper.

At the very least, this must be doable manually, so expenses can be parked like this, and tallied up in the end. Doing that on a unique string (like spot name) could be a suboptimal solution that would still work.

### Service orderings

A lot of camps have services of different kinds, where details has to be added to the order, which can then be reviewed by the service provider afterwards. One example is ordering breakfast that has various details on what they want to order and to whom. That requires either an external system to keep track of this, or perhaps that is something that a POS can be configured for, so the tenant can print out / mail the complete orders for a service.

### Deposits/rents

Various activities requires equipment that must be returned upon completion. Some have have deposits, some have fees and some have both. Some also requires tracking of who actually borrowed the equipment. Here the same goes as for service orderings; either an external system must keep track of this, or perhaps a POS system already has capabilities like this built in.

## Technical requirements

Here you will find requirements that you might face for technical reasons as a POS supplier.

### External users

The users in our system will be owned by our system, and as such, the details for receipts will have to be fetched from there. So if the POS includes user management or receipt management in any way, the details must be externally sourced.

### No tie-ins to hardware

We are aiming for a cloud native setup, so we will just be able to deploy new versions ad hoc. This should also be the case for POS, and thus not require specific hardware, license-keys or whatever, and just be based on logins. Preferably just entirely browser based.

### Test system access

To speed up delivery of new features in our booking system, it is paramount that we are able to run various tests before shipping new features, so we need a highly configurable test system, that includes invoking various flows, to test if the results are the same after our changes.

### Custom coding is done by us

All the integration needed for supporting a POS, will be something we expect to have volunteers coding, to save expenses, but also to be in complete control of the pipeline, and make everything testable, to improve stability across very different tenants.

This sets a high demand on the quality of API or other integration points in a POS.

## Business related requirements

Here you will find our business related requirements to you as a POS supplier.

### Multi-tenant support

We want the experience of using the booking system to be as much plug & play as possible, and thus adding more tenants to the system should be possible trough our system directly, without having to create new accounts in the POS.

This means that we either need to be able to provision new accounts in your system, or that you, preferably, have a tenant-like system already, where we can separate our tenants and administration thereof by an ID, and then centralize administration of all our tenants. That does, however, put strict requirement on separation of tenants, so no data from one tenant is visible to another.

### Varied licensing needs

Some of our tenants are only active one week per year, while others are active half of the year or the entire year, which we need reflected in the pricing model, for them to consider a POS as a valid investment.
