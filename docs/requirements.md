# Requirements

## 1. Project Overview

The Multi-Modal Transport Booking and Journey Management System
is a database-driven system for managing passengers, transport
services, multi-leg journeys, bookings, tickets, payments,
and service disruptions across multiple modes of public transport.

## 2. Users

### Passenger

A passenger can:
- Search available journeys
- View available services
- Make a booking
- View bookings and tickets
- Cancel a booking

### Transport Operator

A transport operator can:
- Manage transport services
- Manage schedules
- Manage vehicles
- Manage routes and stops
- Record service disruptions

### System Administrator

A system administrator can:
- Manage system data
- Monitor bookings
- View operational information

## 3. Main Data Requirements

The system needs to store information about:

- Passengers
- Transport operators
- Transport modes
- Vehicles
- Stations/stops
- Routes
- Transport services
- Journeys
- Journey legs
- Bookings
- Tickets
- Payments
- Service disruptions

## 4. Business Rules

1. A passenger can have multiple bookings.
2. Every booking belongs to exactly one passenger.
3. A journey contains one or more journey legs.
4. Journey legs have a defined sequence.
5. Every journey leg references a valid transport service.
6. Journey legs reference valid origin and destination stops.
7. A confirmed booking cannot exceed available service capacity.
8. A booking can only be confirmed after successful payment.
9. A cancelled booking should no longer consume reserved capacity.
10. A transport service can have zero or more disruptions.
11. A service must have valid departure and arrival times.
12. Consecutive journey legs should connect logically.

## 5. Scope

### Included

- Passenger management
- Transport operators
- Transport modes
- Vehicles
- Stations/stops
- Routes
- Transport services
- Multi-leg journeys
- Bookings
- Tickets
- Payments
- Service disruptions
- Availability checking
- Booking cancellation
- Operational SQL queries
- Database transactions
- Simple Python prototype

### Not Included

- Real-time GPS tracking
- Live public transport APIs
- Actual payment gateways
- Google Maps integration
- Machine-learning predictions
- LLM/AI assistant
- Mobile application
- Advanced route optimisation

## 6. Representative Operations

### OP1 — Search Available Journeys

Find available journeys between two stops for a specified date/time.

### OP2 — Check Service Capacity

Determine the remaining capacity of a transport service.

### OP3 — Book a Multi-Leg Journey

Create a booking for a passenger involving one or more journey legs.

### OP4 — Cancel a Booking

Cancel an existing booking and release the associated capacity.

### OP5 — Manage Service Disruption

Record a disruption and identify affected services and bookings.

## 7. Main Transaction

The main transaction will handle booking a multi-leg journey.

The transaction will:

1. Verify the passenger.
2. Check availability for each journey leg.
3. Create the journey.
4. Create the journey legs.
5. Create the booking.
6. Reserve capacity.
7. Create the ticket.
8. Record payment.
9. Commit the transaction.

If any required step fails, the transaction should be rolled back.
