# Cloud-native booking system

Here you will find details about what Coheir's new cloud-native booking system will be.

## Background

The primary driver is [Å-festival](aa-festival.dk), who is already on their 3rd booking system, the current one being originally developed by [Hjallerup Bibelcamping](www.hjallerupbibelcamping.dk), and going forward being adapted and co-developed with Å-festival. We expect to be able to continue with this going forward, and have had multiple campsites contacting us already, if we have something they can use to solve similar issues they are facing.

## Definitions

To make the language more precise, here is a short vocabulary that will be used going forward:

- Tenant: A single camp or festival that will have their own separated data and userbase

## Major parts

*This section will continuously evolve, as we identify major parts, and each will have their own dedicated page.*

- [Booking process](booking-process.md) - the primary process a user runs trough to book a spot.
- [User management](user-management.md) - the singular service for handling users across multiple software.
- [Economy system](economy-system.md) - the underlying economy system of the booking system - we plan to integrate with an external system for this.
- [POS system](pos-system.md) - the point-of-sales system for managing sales in physical stores and administrative offices - we plan to integrate with an external system for this.
- Booking administration
- Inventory - manage inventory related to the POS.
- Employee apps

## Development stages

The system will be developed in multiple stages with increasing level of configuration and demands. Some demands will greatly affect how the underlying system must be structured from the get-go, and others relates to features that are de-coupled and only relevant for some parties.

### First stage - group booking

The first use-case we need implemented, is a flow where users can only book by grouping and category, and will then be assigned a spot accordingly. The POS needs will be limited, as the related sales are limited, and will be easily added to any POS system.

It still needs to be a complete system with economics, online transactions, e-mail notifications, administration during booking and during related event.

### Second stage - spot booking

The second stage will include the option of choosing the spot to book directly, and thus, tenants can choose either group booking or spot booking as the flow to use. They will be quite different from each other, and thus mutually exclusive for a tenant.

### Third stage - period booking

The third stage will cater to camps that are not event focused, and thus will have different booking periods and also the need to plan vacancies. This will probably use spot booking exclusively as well, but that is yet to be decided.

This stage will also see a huge increase in demands on the POS, because the tenants have actual stores that needs to run professionally, with inventory management, discounts, barcodes etc.

### Fourth stage - hardware integration

There are all sorts of local hardware devices that needs integration - e.g. writing to magnetic cards for entries to areas, showers etc. and making sure these work. This is something we hope to hire people to develop, as it will be time consuming, and targeting for-profit tenants as well. Hopefully this stage will then make the tenants able to switch from their old systems and over to this, even though the system will not be feature complete at this stage, but hopefully, all things considered, still the better option.

## Tech stack

The tech stack is not final yet, but we plan to make it loosely coupled so the right tech stack can be used for the right reasons.
The system *will* be online only though, and managed directly by us. It *will* consist of multiple services (micro service architecture), and able to scale horizontally as demand requires.
