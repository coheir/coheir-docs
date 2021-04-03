# Point Of Sales system

One possible entry point to the booking system, is via staff members booking for customers that show up in person, instead of booking via the website. Doing this can also involve buying other items sold at the same physical position. This in turn leaves us with a need to either develop POS as part of the booking system, or deeply integrate with an already existing solution. We chose the latter, and are here describing what those needs are more specifically.

**work in progress**

## Primary user flows

## Technical requirements

### External users

The users in our system will be owned by our system, and as such, the details for receipts will have to be fetched from there.

## Business related requirements

### Multi-tenant support

We want the experience of using the booking system to be as much plug & play as possible, and thus adding more tenants to the system should be possible trough our system directly, without having to create new accounts in the POS.

## Notes

- Current plan is to use external system for this.
- The POS should be able to handle booking related flows as well.
