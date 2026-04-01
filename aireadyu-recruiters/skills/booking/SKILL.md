---
name: booking
description: >
  Search and book flights, hotels, rental cars, restaurants, and other
  reservations. Multiple providers supported — Amadeus, Google Flights,
  Booking.com, Skyscanner, Kayak, Kiwi, OpenTable, Resy. Use whichever
  the user has configured. Coordinates with calendar after booking.
---

# Booking Skill

Booking handles searching, comparing, and completing reservations for travel,
dining, and appointments. After booking, it creates calendar events and saves
confirmations to the vault.

Multiple providers are listed below. Use whichever provider(s) the user has
configured with API keys. All providers implement the same core operations.

---

## Flight Providers

### Amadeus API

Auth: `AMADEUS_API_KEY` + `AMADEUS_API_SECRET`
API Base: `https://api.amadeus.com`
Free self-service tier. Industry standard.

```bash
# Get token
curl -X POST https://api.amadeus.com/v1/security/oauth2/token \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "grant_type=client_credentials&client_id=$AMADEUS_API_KEY&client_secret=$AMADEUS_API_SECRET"

# Search flights
curl "https://api.amadeus.com/v2/shopping/flight-offers?originLocationCode=AUS&destinationLocationCode=SFO&departureDate=2026-06-10&returnDate=2026-06-15&adults=1&max=5" \
  -H "Authorization: Bearer $AMADEUS_TOKEN"

# Search airports/cities
curl "https://api.amadeus.com/v1/reference-data/locations?subType=AIRPORT,CITY&keyword=austin" \
  -H "Authorization: Bearer $AMADEUS_TOKEN"
```

### Google Flights (via SerpApi)

Auth: `SERPAPI_KEY`
API Base: `https://serpapi.com/search`
Google Flights has no public API. SerpApi scrapes it.

```bash
curl "https://serpapi.com/search.json?engine=google_flights&departure_id=AUS&arrival_id=SFO&outbound_date=2026-06-10&return_date=2026-06-15&adults=1&api_key=$SERPAPI_KEY"
```

### Skyscanner API (via RapidAPI)

Auth: `RAPIDAPI_KEY`
API Base: `https://skyscanner80.p.rapidapi.com/api/v1`

```bash
# Search flights
curl "https://skyscanner80.p.rapidapi.com/api/v1/flights/searchFlights?fromId=AUS&toId=SFO&departDate=2026-06-10&returnDate=2026-06-15&adults=1" \
  -H "x-rapidapi-key: $RAPIDAPI_KEY" \
  -H "x-rapidapi-host: skyscanner80.p.rapidapi.com"
```

### Kayak (via SerpApi)

Auth: `SERPAPI_KEY`

```bash
curl "https://serpapi.com/search.json?engine=kayak&search_type=flights&from=AUS&to=SFO&depart_date=2026-06-10&return_date=2026-06-15&adults=1&api_key=$SERPAPI_KEY"
```

### Kiwi / Tequila API

Auth: `KIWI_API_KEY`
API Base: `https://api.tequila.kiwi.com`
Good for multi-city and flexible date searches.

```bash
curl "https://api.tequila.kiwi.com/v2/search?fly_from=AUS&fly_to=SFO&date_from=10/06/2026&date_to=10/06/2026&return_from=15/06/2026&return_to=15/06/2026&adults=1&curr=USD&limit=5" \
  -H "apikey: $KIWI_API_KEY"
```

---

## Hotel Providers

### Amadeus Hotel Search

```bash
# Search hotels by city
curl "https://api.amadeus.com/v1/reference-data/locations/hotels/by-city?cityCode=SFO&radius=10&radiusUnit=MILE" \
  -H "Authorization: Bearer $AMADEUS_TOKEN"

# Get pricing
curl "https://api.amadeus.com/v3/shopping/hotel-offers?hotelIds=HOTEL_ID&checkInDate=2026-06-10&checkOutDate=2026-06-15&adults=1" \
  -H "Authorization: Bearer $AMADEUS_TOKEN"
```

### Booking.com (via RapidAPI)

Auth: `RAPIDAPI_KEY`

```bash
curl "https://booking-com15.p.rapidapi.com/api/v1/hotels/searchHotels?dest_id=20015732&search_type=CITY&arrival_date=2026-06-10&departure_date=2026-06-15&adults=1&room_qty=1&currency_code=USD" \
  -H "x-rapidapi-key: $RAPIDAPI_KEY" \
  -H "x-rapidapi-host: booking-com15.p.rapidapi.com"
```

### Google Hotels (via SerpApi)

```bash
curl "https://serpapi.com/search.json?engine=google_hotels&q=hotels+in+san+francisco&check_in_date=2026-06-10&check_out_date=2026-06-15&adults=1&api_key=$SERPAPI_KEY"
```

---

## Restaurant Providers

### OpenTable

Auth: `OPENTABLE_TOKEN`

```bash
curl "https://api.opentable.com/v2/restaurants?city=Austin&per_page=10" \
  -H "Authorization: Bearer $OPENTABLE_TOKEN"
```

### Resy (via browser automation)

Resy has no public API. Use browser automation:

```bash
npx playwright open "https://resy.com/cities/austin?query=italian"
```

### Google Maps Places API

Auth: `GOOGLE_MAPS_API_KEY`
Good for discovery and reviews.

```bash
curl "https://maps.googleapis.com/maps/api/place/textsearch/json?query=restaurants+in+austin&key=$GOOGLE_MAPS_API_KEY"
```

---

## Rental Cars

### Amadeus Car Search

```bash
curl "https://api.amadeus.com/v1/shopping/car-offers?pickUpLocationCode=SFO&pickUpDate=2026-06-10&dropOffDate=2026-06-15" \
  -H "Authorization: Bearer $AMADEUS_TOKEN"
```

### Kayak Car Rentals (via SerpApi)

```bash
curl "https://serpapi.com/search.json?engine=kayak&search_type=cars&pickup=SFO&dropoff=SFO&pickup_date=2026-06-10&dropoff_date=2026-06-15&api_key=$SERPAPI_KEY"
```

---

## Provider Selection Guide

| Need | Best Provider |
|------|--------------|
| Cheapest flights | Kiwi (flexible), Skyscanner (aggregator) |
| Specific airline/loyalty | Amadeus (direct inventory) |
| Quick comparison | Google Flights via SerpApi, Kayak via SerpApi |
| Hotels with reviews | Booking.com, Google Hotels |
| Hotel pricing/availability | Amadeus |
| Restaurant reservations | OpenTable (API), Resy (automation) |
| Restaurant discovery | Google Maps Places |
| Rental cars | Amadeus, Kayak |
| Multi-city complex trips | Kiwi Tequila |

---

## Post-Booking Protocol

After every successful booking:

1. **Confirm** — retrieve confirmation number and full details
2. **Calendar** — create an event via the `calendar` skill:
   - Summary: booking type + destination/provider
   - Description: confirmation number, cancellation policy, vault path
   - Time: departure/check-in to return/check-out
3. **Vault** — save confirmation via `storage`:
   - Flights, hotels, rental cars → `play/00_current/` or `transit/00_current/`
   - Medical appointments → `health/00_current/`
   - Legal appointments → `legal/00_current/`
   - Financial appointments → `wealth/00_current/` or `tax/00_current/`
4. **Notify** — inform the calling agent with full details

## Usage Rules

- Always confirm preferences before booking (seat class, loyalty programs, hotel brands, dietary restrictions)
- Never complete a booking without explicit user approval for the specific option
- Note cancellation policies at time of booking
- Store loyalty program numbers for use in bookings
- When comparing, present a clear table: price, duration, stops, airline/hotel, cancellation policy

## Vault Integration

Save every confirmation:
- Name: `YYYY-MM-DD_booking-type-destination.md`
- Include: confirmation number, dates, provider, cost, cancellation policy
- Path: `play/00_current/` for leisure, `transit/00_current/` for transport, domain-specific for appointments
