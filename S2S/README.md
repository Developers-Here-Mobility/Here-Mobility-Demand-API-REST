marketplace/public/grpc/demand_handler/v2/demand_s2s_service.proto-REST
=======================================================================
**Version:** version not set

### /demand.v2.s2s/offers
---
##### ***GET***
**Summary:** *  Get ride offers based on a ride request. May take a few seconds. When no offers are available, returns an empty response.
Errors:
INVALID_ARGUMENT: Invalid field value. For example: prebook_pickup_time is in the past, route.pickup.lat is not a valid latitude, etc.

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| user_id | query | Mandatory. The ID of the user requesting the ride. | No | string |
| route.pickup.point.lat | query | Latitude. | No | double |
| route.pickup.point.lng | query | Longitude. | No | double |
| route.pickup.address.country | query | Localized country name. | No | string |
| route.pickup.address.country_code | query | ISO 3166-alpha-3 country code. | No | string |
| route.pickup.address.state | query | State (first subdivision level below the country, if relevant). | No | string |
| route.pickup.address.county | query | County (second subdivision level below the country, if relevant). | No | string |
| route.pickup.address.city | query | City/town. | No | string |
| route.pickup.address.district | query | District (subdivision level below the city). | No | string |
| route.pickup.address.sub_district | query | Sub-district (subdivision level below the district; e.g. commonly used in IND). | No | string |
| route.pickup.address.street | query | Street name. | No | string |
| route.pickup.address.house_number | query | House number; depending on regional characteristics, can also be house name. | No | string |
| route.pickup.address.postal_code | query | Postal code (zipcode). | No | string |
| route.pickup.address.building | query | Building name; e.g. commonly used in HKG. | No | string |
| route.pickup.address.line | query | Formatted address lines. | No | [ string ] |
| route.pickup.free_text | query | Optional. Street address in a free text format. | No | string |
| route.pickup.place.name | query | The place name. | No | string |
| route.pickup.place.category | query | The place category (e.g.: Airport, Restaurant, Park, etc.).   - RESTAURANT: An establishment that prepares and serves refreshments and prepared meals.  - COFFEE_TEA: An establishment that sells drinks, such as coffee and tea, as well as refreshments.  - NIGHTLIFE: An establishment that provides evening entertainment and usually serves alcoholic beverages.  - CINEMA: An establishment that shows movies through screen projection.  - CULTURE: An establishment where various types of performing arts are presented.  - GAMBLING_LOTTERY: An establishment that provides gambling entertainment.  - ATTRACTION: A designated area of special interest to tourists.  - MUSEUM: An establishment dedicated to the preservation and exhibition of artistic, historical, or scientific artifacts.  - RELIGIOUS_PLACE: An establishment of special religious significance or where religious services are held.  - WATER: A natural and geographical feature of the earth's surface that is covered with water, such as a lake, river, stream or ocean.  - MOUNTAIN: A natural and geographical feature that is higher than the surrounding land.  - UNDERSEA: Undersea attractions  - FOREST: A forest, heath or other vegetation  - GEOGRAPHICAL: Natural and geographical locations  - AIRPORT: A designated area that serves various aspects of aviation related sports, including gliders, recreational aircraft and model airplanes.  - PUBLIC_TRANSPORTATION: A facility for travelers who are travelling between stops on public transport.  - CARGO_TRANSPORTATION: A facility that handles some aspect of the transportation of cargo freight.  - REST_AREA: An establishment along a motorway (controlled access road) that provides restrooms and parking.  - HOTEL: A business that provides lodging or temporary living quarters.  - LODGE: A business that provides lodging to the public generally without room service.  - OUTDOORS: Public land preserved and maintained for recreational use.  - LEISURE: A park that contains rides and/or other entertainment which may be based on a central theme.  - CONVENIENCE_STORE: An establishment that sells groceries, candy, toiletries, soft drinks, tobacco products, newspapers and other products.  - SHOPPING_CENTER: A complex of businesses that are co-located and share common services.  - DEPARTMENT_STORE: A business that sells a wide variety of merchandise that is organized by product or service departments.  - FOOD_AND_DRINKS: A business that sells specialty products of a particular type of food or beverage.  - PHARMACY: A business that sells medications, toiletry items and other retail cosmetics.  - ELECTRONICS: A business that sells consumer electronics and electronic entertainment equipment.  - HARDWARE_HOUSE_GARDEN: A business that sells crafts, gardening, remodeling, or decorating items for the home.  - BOOKSTORE: A business that sells books, magazines and other reading material.  - CLOTHING_AND_ACCESSORIES: A business that sells apparel items, garments or fashion accessories for men, women, and children.  - STORE: A business that sells a variety of products targeted to consumers.  - HAIR_BEAUTY: A business that provides hair styling and personal appearance services. Places in this category may also sell hair products and other related cosmetic items.  - BANKING: Businesses that specialize in the maintenance, lending, exchange, or issuance of money.  - ATM: A computer terminal that allows bank customers to deposit, withdraw, or transfer funds without the assistance of a bank teller.  - MONEY_SERVICES: Businesses that provide money related services.  - MEDIA: Businesses that provide communication services.  - COMMERCIAL_SERVICES: Businesses that provide a service or product for use by other businesses.  - BUSINESS_INDUSTRY: Businesses that employ people in and around the city in which it is located.  - EMERGANCY_SERVICES: Municipal emergency services  - CONSUMER_SERVICES: An organization that provides consumer services for a variety of products for used by the public.  - POST_OFFICE: An office or station that receives, sorts, dispatches and delivers mail to a specific area or region.  - TOOURIST_INFORMATION: Businesses that provide a variety of information for visiting tourists, such as event schedules, lodging/accommodations, restaurants, attractions and more  - FEUL_STATION: Businesses that sell fuel for vehicles  - CAR_DEALER: Businesses that sell new automobiles and motorcycles.  - CAR_REPAIR: Businesses that provide automotive repair services.  - CAR_RENTAL: Businesses that rent or lease automobiles.  - TRUCK_SERVICES: Business that sell or service trucks and tractor trailers.  - HEALTH_CARE: Facilities that include dental offices, hospitals, nursing homes and other health care-related services.  - GOVERNMENT: A Place where government services are provided.  - EDUCATION: Facilities that are used for educational purposes including primary schooling, secondary schooling, universities and more.  - LIBRARY: Facilities that offer books, periodicals, audio, video and other material for public use.  - EVENTS: An area or facility used for the hosting of fairs and conventions.  - PARKING: Area or building used for parking cars  - SPORTS: A facility used for individual and team sports including recreational sports.  - FACILITIES: Facilities with miscellaneous uses such as Clubhouses, Offices, and Registration Offices.  - CITY: Represents a named settlement that may be a (large) city, town, or tiny village  - OUTDOORS_COMPLEX: Outdoor areas or complexes with designations for specific businesses or interests.  - BUILDING: Areas and buildings designated for residential or office use  - ADMINISTRATIVE_REGION: An administrative region, such as a postal area, or a named street/square/intersection. | No | string |
| route.destination.point.lat | query | Latitude. | No | double |
| route.destination.point.lng | query | Longitude. | No | double |
| route.destination.address.country | query | Localized country name. | No | string |
| route.destination.address.country_code | query | ISO 3166-alpha-3 country code. | No | string |
| route.destination.address.state | query | State (first subdivision level below the country, if relevant). | No | string |
| route.destination.address.county | query | County (second subdivision level below the country, if relevant). | No | string |
| route.destination.address.city | query | City/town. | No | string |
| route.destination.address.district | query | District (subdivision level below the city). | No | string |
| route.destination.address.sub_district | query | Sub-district (subdivision level below the district; e.g. commonly used in IND). | No | string |
| route.destination.address.street | query | Street name. | No | string |
| route.destination.address.house_number | query | House number; depending on regional characteristics, can also be house name. | No | string |
| route.destination.address.postal_code | query | Postal code (zipcode). | No | string |
| route.destination.address.building | query | Building name; e.g. commonly used in HKG. | No | string |
| route.destination.address.line | query | Formatted address lines. | No | [ string ] |
| route.destination.free_text | query | Optional. Street address in a free text format. | No | string |
| route.destination.place.name | query | The place name. | No | string |
| route.destination.place.category | query | The place category (e.g.: Airport, Restaurant, Park, etc.).   - RESTAURANT: An establishment that prepares and serves refreshments and prepared meals.  - COFFEE_TEA: An establishment that sells drinks, such as coffee and tea, as well as refreshments.  - NIGHTLIFE: An establishment that provides evening entertainment and usually serves alcoholic beverages.  - CINEMA: An establishment that shows movies through screen projection.  - CULTURE: An establishment where various types of performing arts are presented.  - GAMBLING_LOTTERY: An establishment that provides gambling entertainment.  - ATTRACTION: A designated area of special interest to tourists.  - MUSEUM: An establishment dedicated to the preservation and exhibition of artistic, historical, or scientific artifacts.  - RELIGIOUS_PLACE: An establishment of special religious significance or where religious services are held.  - WATER: A natural and geographical feature of the earth's surface that is covered with water, such as a lake, river, stream or ocean.  - MOUNTAIN: A natural and geographical feature that is higher than the surrounding land.  - UNDERSEA: Undersea attractions  - FOREST: A forest, heath or other vegetation  - GEOGRAPHICAL: Natural and geographical locations  - AIRPORT: A designated area that serves various aspects of aviation related sports, including gliders, recreational aircraft and model airplanes.  - PUBLIC_TRANSPORTATION: A facility for travelers who are travelling between stops on public transport.  - CARGO_TRANSPORTATION: A facility that handles some aspect of the transportation of cargo freight.  - REST_AREA: An establishment along a motorway (controlled access road) that provides restrooms and parking.  - HOTEL: A business that provides lodging or temporary living quarters.  - LODGE: A business that provides lodging to the public generally without room service.  - OUTDOORS: Public land preserved and maintained for recreational use.  - LEISURE: A park that contains rides and/or other entertainment which may be based on a central theme.  - CONVENIENCE_STORE: An establishment that sells groceries, candy, toiletries, soft drinks, tobacco products, newspapers and other products.  - SHOPPING_CENTER: A complex of businesses that are co-located and share common services.  - DEPARTMENT_STORE: A business that sells a wide variety of merchandise that is organized by product or service departments.  - FOOD_AND_DRINKS: A business that sells specialty products of a particular type of food or beverage.  - PHARMACY: A business that sells medications, toiletry items and other retail cosmetics.  - ELECTRONICS: A business that sells consumer electronics and electronic entertainment equipment.  - HARDWARE_HOUSE_GARDEN: A business that sells crafts, gardening, remodeling, or decorating items for the home.  - BOOKSTORE: A business that sells books, magazines and other reading material.  - CLOTHING_AND_ACCESSORIES: A business that sells apparel items, garments or fashion accessories for men, women, and children.  - STORE: A business that sells a variety of products targeted to consumers.  - HAIR_BEAUTY: A business that provides hair styling and personal appearance services. Places in this category may also sell hair products and other related cosmetic items.  - BANKING: Businesses that specialize in the maintenance, lending, exchange, or issuance of money.  - ATM: A computer terminal that allows bank customers to deposit, withdraw, or transfer funds without the assistance of a bank teller.  - MONEY_SERVICES: Businesses that provide money related services.  - MEDIA: Businesses that provide communication services.  - COMMERCIAL_SERVICES: Businesses that provide a service or product for use by other businesses.  - BUSINESS_INDUSTRY: Businesses that employ people in and around the city in which it is located.  - EMERGANCY_SERVICES: Municipal emergency services  - CONSUMER_SERVICES: An organization that provides consumer services for a variety of products for used by the public.  - POST_OFFICE: An office or station that receives, sorts, dispatches and delivers mail to a specific area or region.  - TOOURIST_INFORMATION: Businesses that provide a variety of information for visiting tourists, such as event schedules, lodging/accommodations, restaurants, attractions and more  - FEUL_STATION: Businesses that sell fuel for vehicles  - CAR_DEALER: Businesses that sell new automobiles and motorcycles.  - CAR_REPAIR: Businesses that provide automotive repair services.  - CAR_RENTAL: Businesses that rent or lease automobiles.  - TRUCK_SERVICES: Business that sell or service trucks and tractor trailers.  - HEALTH_CARE: Facilities that include dental offices, hospitals, nursing homes and other health care-related services.  - GOVERNMENT: A Place where government services are provided.  - EDUCATION: Facilities that are used for educational purposes including primary schooling, secondary schooling, universities and more.  - LIBRARY: Facilities that offer books, periodicals, audio, video and other material for public use.  - EVENTS: An area or facility used for the hosting of fairs and conventions.  - PARKING: Area or building used for parking cars  - SPORTS: A facility used for individual and team sports including recreational sports.  - FACILITIES: Facilities with miscellaneous uses such as Clubhouses, Offices, and Registration Offices.  - CITY: Represents a named settlement that may be a (large) city, town, or tiny village  - OUTDOORS_COMPLEX: Outdoor areas or complexes with designations for specific businesses or interests.  - BUILDING: Areas and buildings designated for residential or office use  - ADMINISTRATIVE_REGION: An administrative region, such as a postal area, or a named street/square/intersection. | No | string |
| constraints.passengers_no | query | The number of passengers (1 or more). | No | long |
| constraints.suitcases_no | query | The number of suitcases (0 or more). | No | long |
| prebook_pickup_time_ms | query | Optional. For taxi rides, this should be a future pickup time, which is at least 30 minutes after the request time. For public transport rides this can be any pickup time that is not in the past. In all cases, an empty value indicates a request for an immediate ride. | No | string (uint64) |
| price_range.lower_bound | query | The range’s lower limit, for example: "12.5", "12", etc. Unsigned. | No | string |
| price_range.upper_bound | query | The range’s upper limit, for example: "12.5", "12", etc. Unsigned. | No | string |
| price_range.currency_code | query | The price currency. An ISO 4217 Currency Code, for example: "USD", "EUR", "JPY". | No | string |
| sort_type | query | FUTURE FEATURE, CURRENTLY UNSUPPORTED: Optional. How to sort the RideOffers, by price or by ETA. (The Marketplace default sort order is by best price, and then minimal ETA.).   - BY_PRICE: Sort by price (lowest price first).  - BY_ETA: Sort by arrival time (earliest arrival time first). | No | string |
| passenger_note | query | Optional. A free text note from the passenger. | No | string |
| transit_options.max_transfers | query | Optional. Maximum number of changes or transfers allowed in a route. Default is unlimited. Range is 0-6. | No | integer |
| transit_options.max_walking_distance_meters | query | Optional. Specifies a maximum walking distance in meters. Default is 2000. Range is 0-6000. | No | integer |
| transit_options.locale | query | DEPRECATED!! please use the locale found in RideOffersRequest. | No | string |
| payment_constraints | query | Optional. Parameters for supported payment flows. Defualt is SUPPORTS_OFFLINE. | No | string |
| transport_type_preference.use_taxi | query |  | No | boolean (boolean) |
| transport_type_preference.use_public_transport | query |  | No | boolean (boolean) |
| locale | query | Optional. Should indicates clients's locale. - ISO-639-1 standard language codes, defaults to "en". - ISO-3166-1-alpha-2 country codes - example: "en-US" (US is the ISO 3166‑1 country code for the United States) Based on IETF language tag best practice as specified by https://tools.ietf.org/html/rfc5646. | No | string |
| max_number_of_offers.value | query | The uint32 value. | No | long |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonRideOffersResponse](#commonrideoffersresponse) |

### /demand.v2.s2s/offertracker/{offer_tracking_id}
---
##### ***GET***
**Summary:** Returns the offer by offer tracking ID
Errors:
INVALID_ARGUMENT - offer tracking id was not supplied
NOT_FOUND - offer not found for the specified offer tracking ID, or offer tracking ID is invalid

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| offer_tracking_id | path |  | Yes | string |
| transit_type | query | Mandatory. The transit type of the offer.   - UNKNOWN_TRANSIT_TYPE: Unknown transit type.  - TAXI: Taxi ride  - PUBLIC_TRANSPORT: Public transport ride. | No | string |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonRideOffer](#commonrideoffer) |

### /demand.v2.s2s/publictransport
---
##### ***POST***
**Summary:** Notify the marketplace that a public transportation offer was chosen

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body |  | Yes | [s2sCreatePublicTransportRideRequest](#s2screatepublictransportriderequest) |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonEmpty](#commonempty) |

### /demand.v2.s2s/rides
---
##### ***GET***
**Summary:** * Get rides for all users.
Returns rides that were updated recently (in the last 3 hours(OnGoing)/180 days(Future)/14 days(Past), or after the given from_update_time).

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| query.from_time_ms | query | Optional. Filters rides according to update or creation time (depending on the sort type). When the sort is UPDATE_TIME_ASC, returns rides UPDATED AFTER this time. When the sort is UPDATE_TIME_DESC, returns rides UPDATED BEFORE this time. When the sort is CREATE_TIME_ASC, returns rides CREATED AFTER this time. When the sort is CREATE_TIME_DESC, return rides CREATED BEFORE this time.  Default value for ascending sort orders is NOW-3 hours, expect for FUTURE or PAST rides. Default value for FUTURE rides is Now-180 days. Default value for PAST rides is NOW-14 days. Default value for descending sort orders is NOW. This value is in UTC (milliseconds since Epoch time). | No | string (uint64) |
| query.limit | query | Optional. The maximal number of rides to return. When not set, the default is 200. | No | long |
| query.status_filter | query | Optional. Return only rides with the given status. When not set, rides with all statuses are returned.   - UNKNOWN_RIDE_STATUS_FILTER: Unknown ride status.  - PAST: Terminated rides (includes the statuses: COMPLETED, REJECTED or CANCELLED). Default: in the past 14 days.  - FUTURE: Pre-booked rides in status PROCESSING or ACCEPTED. Default: in the past 180 days.  - ONGOING: Ongoing rides (all rides other than PAST and FUTURE). Default: in the past 3 hours.  - ALL: All rides. | No | string |
| query.sort_by | query | Optional. Default is UPDATE_TIME_ASC.   - UNKNOWN_SORT_TYPE: Unknown sort order.  - UPDATE_TIME_ASC: Ascending order of update time.  - UPDATE_TIME_DESC: Descending order of update time.  - CREATE_TIME_ASC: Ascending order of creation time.  - CREATE_TIME_DESC: Descending order of creation time. | No | string |
| get_all_apps | query | Optional. Get rides from all applications. | No | boolean (boolean) |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonRideQueryResponse](#commonridequeryresponse) |

##### ***POST***
**Summary:** * Create a new ride based on an offer ID. If the offer is valid, a ride is returned immediately with the status PROCESSING.

**Description:** Errors:
NOT_FOUND: The offer ID is expired or does not exist
ALREADY_EXISTS: A booking already exists for this offer ID (call GetRideOffers to receive new offer IDs).

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body |  | Yes | [s2sCreateRideRequest](#s2screateriderequest) |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonRide](#commonride) |

### /demand.v2.s2s/rides/by_user/{user_id}
---
##### ***GET***
**Summary:** * Get rides for a single user.
Returns rides that were updated recently (in the last 3 hours, or after the given from_update_time).

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| user_id | path |  | Yes | string |
| query.from_time_ms | query | Optional. Filters rides according to update or creation time (depending on the sort type). When the sort is UPDATE_TIME_ASC, returns rides UPDATED AFTER this time. When the sort is UPDATE_TIME_DESC, returns rides UPDATED BEFORE this time. When the sort is CREATE_TIME_ASC, returns rides CREATED AFTER this time. When the sort is CREATE_TIME_DESC, return rides CREATED BEFORE this time.  Default value for ascending sort orders is NOW-3 hours, expect for FUTURE or PAST rides. Default value for FUTURE rides is Now-180 days. Default value for PAST rides is NOW-14 days. Default value for descending sort orders is NOW. This value is in UTC (milliseconds since Epoch time). | No | string (uint64) |
| query.limit | query | Optional. The maximal number of rides to return. When not set, the default is 200. | No | long |
| query.status_filter | query | Optional. Return only rides with the given status. When not set, rides with all statuses are returned.   - UNKNOWN_RIDE_STATUS_FILTER: Unknown ride status.  - PAST: Terminated rides (includes the statuses: COMPLETED, REJECTED or CANCELLED). Default: in the past 14 days.  - FUTURE: Pre-booked rides in status PROCESSING or ACCEPTED. Default: in the past 180 days.  - ONGOING: Ongoing rides (all rides other than PAST and FUTURE). Default: in the past 3 hours.  - ALL: All rides. | No | string |
| query.sort_by | query | Optional. Default is UPDATE_TIME_ASC.   - UNKNOWN_SORT_TYPE: Unknown sort order.  - UPDATE_TIME_ASC: Ascending order of update time.  - UPDATE_TIME_DESC: Descending order of update time.  - CREATE_TIME_ASC: Ascending order of creation time.  - CREATE_TIME_DESC: Descending order of creation time. | No | string |
| get_all_apps | query | Optional. Get rides from all applications. | No | boolean (boolean) |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonRideQueryResponse](#commonridequeryresponse) |

### /demand.v2.s2s/rides/{ride_id}
---
##### ***GET***
**Summary:** * Get a ride by ID. Use this call to poll for the ride status (every 10 seconds).
NOTE: The status of closed rides (COMPLETED, CANCELLED, REJECTED) never changes.
Errors:
NOT_FOUND: Ride does not exist.

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| ride_id | path |  | Yes | string |
| user_id | query | Optional. The ID of the requesting user. | No | string |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonRide](#commonride) |

### /demand.v2.s2s/rides/{ride_id}/cancel
---
##### ***PUT***
**Summary:** * Cancel a ride. Returns immediately without waiting for a response from the supplier.
Errors:
NOT_FOUND: Ride does not exist.
FAILED_PRECONDITION: Cancel is not allowed by policy, or because the ride status is REJECTED, COMPLETED, or CANCELLED.

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| ride_id | path |  | Yes | string |
| body | body |  | Yes | [s2sCancelRideRequest](#s2scancelriderequest) |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonEmpty](#commonempty) |

### /demand.v2.s2s/rides/{ride_id}/location
---
##### ***GET***
**Summary:** Returns the geo-location of the ride. Use this call to poll for the ride location (every 10 seconds)
NOTES:
Test the flag Ride.status_log.is_ride_location_available, to learn whether ride locations are supported.
Rides which are closed (COMPLETED, CANCELLED, REJECTED) never change their location.
Errors:
NOT_FOUND: Ride does not exist

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| ride_id | path |  | Yes | string |
| user_id | query | Optional. The ID of the requesting user. | No | string |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonRideLocation](#commonridelocation) |

### /demand.v2.s2s/rides/{ride_id}/payment
---
##### ***GET***
**Summary:** returns the Online payment details
NOT_FOUND - ride not found or PaymentFlow is ont online

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| ride_id | path |  | Yes | string |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonRidePayment](#commonridepayment) |

### /demand.v2.s2s/ridetracker/{ride_tracking_id}
---
##### ***GET***
**Summary:** Returns the ride tracking details by ride tracking ID
Errors:
INVALID_ARGUMENT - ride tracking id was not supplied
NOT_FOUND - ride not found for the specified ride tracking ID, or ride tracking ID is invalid

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| ride_tracking_id | path |  | Yes | string |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonRideTrackingDetails](#commonridetrackingdetails) |

### /demand.v2.s2s/ridetracker/{ride_tracking_id}/cancel
---
##### ***POST***
**Summary:** Cancel a tracked ride by ride tracking ID.
validation is done by comparing the request passenger phone to the passenger phone number as retrieved
in Create Ride Request
Errors:
INVALID_ARGUMENT - ride tracking id or passenger phone were not supplied
NOT_FOUND - ride not found for the specified ride tracking ID, or ride tracking ID is invalid
UNAUTHENTICATED: Validation failed for the given passenger phone number

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| ride_tracking_id | path |  | Yes | string |
| body | body |  | Yes | [s2sCancelTrackedRideRequest](#s2scanceltrackedriderequest) |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonEmpty](#commonempty) |

### /demand.v2.s2s/verticalscoverage
---
##### ***GET***
**Summary:** Returns the verticals in which the point is covered

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| point.lat | query | Latitude. | No | double |
| point.lng | query | Longitude. | No | double |
| filter_by_restrictions | query | Optional. Required to filter blacklist/whitelist suppliers. Default - false. | No | boolean (boolean) |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonVerticalsCoverageResponse](#commonverticalscoverageresponse) |

### Models
---

### CancellationInfoCancelReasonCategory

 - UNKNOWN_CANCEL_REASON_CATEGORY: Unknown cancellation category.
 - DRIVER_NO_SHOW: Passenger cancellation category.
 - PRICE_CHANGED: Passenger cancellation category.
 - ETA_CHANGED: Passenger cancellation category.
 - UNSUITABLE_VEHICLE: Passenger cancellation category.
 - DRIVER_BEHAVED_INAPPROPRIATELY: Passenger cancellation category.
 - CHANGED_MY_PLANS: Passenger cancellation category.
 - DRIVERS_UNAVAILABLE: Supplier cancellation category.
 - PASSENGER_NO_SHOW: Supplier cancellation category.
 - PASSENGER_REQUESTED_TO_CANCEL: Supplier cancellation category.
 - VEHICLE_MALFUNCTION: Supplier cancellation category.
 - HEAVY_TRAFFIC: Supplier cancellation category.
 - OTHER_CANCEL_REASON_CATEGORY: Supplier or passenger cancellation category.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| CancellationInfoCancelReasonCategory | string |  - UNKNOWN_CANCEL_REASON_CATEGORY: Unknown cancellation category.
 - DRIVER_NO_SHOW: Passenger cancellation category.
 - PRICE_CHANGED: Passenger cancellation category.
 - ETA_CHANGED: Passenger cancellation category.
 - UNSUITABLE_VEHICLE: Passenger cancellation category.
 - DRIVER_BEHAVED_INAPPROPRIATELY: Passenger cancellation category.
 - CHANGED_MY_PLANS: Passenger cancellation category.
 - DRIVERS_UNAVAILABLE: Supplier cancellation category.
 - PASSENGER_NO_SHOW: Supplier cancellation category.
 - PASSENGER_REQUESTED_TO_CANCEL: Supplier cancellation category.
 - VEHICLE_MALFUNCTION: Supplier cancellation category.
 - HEAVY_TRAFFIC: Supplier cancellation category.
 - OTHER_CANCEL_REASON_CATEGORY: Supplier or passenger cancellation category. |  |

### CancellationInfoParty

 - UNKNOWN: The cancelling party is unknown.
 - DEMANDER: The demander cancelled the ride (e.g. concierge).
 - SUPPLIER: The supplier cancelled the ride.
 - PASSENGER: The passenger cancelled the ride.
 - MARKETPLACE: MP cancelled the ride.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| CancellationInfoParty | string |  - UNKNOWN: The cancelling party is unknown.
 - DEMANDER: The demander cancelled the ride (e.g. concierge).
 - SUPPLIER: The supplier cancelled the ride.
 - PASSENGER: The passenger cancelled the ride.
 - MARKETPLACE: MP cancelled the ride. |  |

### CancellationInfoStatusReason

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| CancellationInfoStatusReason | string |  |  |

### FareFareItem

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| amount_in_cents | string (uint64) |  | No |
| type | [FareFareItemType](#farefareitemtype) |  | No |

### FareFareItemType

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| FareFareItemType | string |  |  |

### PlacePlaceCategory

 - RESTAURANT: An establishment that prepares and serves refreshments and prepared meals.
 - COFFEE_TEA: An establishment that sells drinks, such as coffee and tea, as well as refreshments.
 - NIGHTLIFE: An establishment that provides evening entertainment and usually serves alcoholic beverages.
 - CINEMA: An establishment that shows movies through screen projection.
 - CULTURE: An establishment where various types of performing arts are presented.
 - GAMBLING_LOTTERY: An establishment that provides gambling entertainment.
 - ATTRACTION: A designated area of special interest to tourists.
 - MUSEUM: An establishment dedicated to the preservation and exhibition of artistic, historical, or scientific artifacts.
 - RELIGIOUS_PLACE: An establishment of special religious significance or where religious services are held.
 - WATER: A natural and geographical feature of the earth's surface that is covered with water, such as a lake, river, stream or ocean.
 - MOUNTAIN: A natural and geographical feature that is higher than the surrounding land.
 - UNDERSEA: Undersea attractions
 - FOREST: A forest, heath or other vegetation
 - GEOGRAPHICAL: Natural and geographical locations
 - AIRPORT: A designated area that serves various aspects of aviation related sports, including gliders, recreational aircraft and model airplanes.
 - PUBLIC_TRANSPORTATION: A facility for travelers who are travelling between stops on public transport.
 - CARGO_TRANSPORTATION: A facility that handles some aspect of the transportation of cargo freight.
 - REST_AREA: An establishment along a motorway (controlled access road) that provides restrooms and parking.
 - HOTEL: A business that provides lodging or temporary living quarters.
 - LODGE: A business that provides lodging to the public generally without room service.
 - OUTDOORS: Public land preserved and maintained for recreational use.
 - LEISURE: A park that contains rides and/or other entertainment which may be based on a central theme.
 - CONVENIENCE_STORE: An establishment that sells groceries, candy, toiletries, soft drinks, tobacco products, newspapers and other products.
 - SHOPPING_CENTER: A complex of businesses that are co-located and share common services.
 - DEPARTMENT_STORE: A business that sells a wide variety of merchandise that is organized by product or service departments.
 - FOOD_AND_DRINKS: A business that sells specialty products of a particular type of food or beverage.
 - PHARMACY: A business that sells medications, toiletry items and other retail cosmetics.
 - ELECTRONICS: A business that sells consumer electronics and electronic entertainment equipment.
 - HARDWARE_HOUSE_GARDEN: A business that sells crafts, gardening, remodeling, or decorating items for the home.
 - BOOKSTORE: A business that sells books, magazines and other reading material.
 - CLOTHING_AND_ACCESSORIES: A business that sells apparel items, garments or fashion accessories for men, women, and children.
 - STORE: A business that sells a variety of products targeted to consumers.
 - HAIR_BEAUTY: A business that provides hair styling and personal appearance services. Places in this category may also sell hair products and other related cosmetic items.
 - BANKING: Businesses that specialize in the maintenance, lending, exchange, or issuance of money.
 - ATM: A computer terminal that allows bank customers to deposit, withdraw, or transfer funds without the assistance of a bank teller.
 - MONEY_SERVICES: Businesses that provide money related services.
 - MEDIA: Businesses that provide communication services.
 - COMMERCIAL_SERVICES: Businesses that provide a service or product for use by other businesses.
 - BUSINESS_INDUSTRY: Businesses that employ people in and around the city in which it is located.
 - EMERGANCY_SERVICES: Municipal emergency services
 - CONSUMER_SERVICES: An organization that provides consumer services for a variety of products for used by the public.
 - POST_OFFICE: An office or station that receives, sorts, dispatches and delivers mail to a specific area or region.
 - TOOURIST_INFORMATION: Businesses that provide a variety of information for visiting tourists, such as event schedules, lodging/accommodations, restaurants, attractions and more
 - FEUL_STATION: Businesses that sell fuel for vehicles
 - CAR_DEALER: Businesses that sell new automobiles and motorcycles.
 - CAR_REPAIR: Businesses that provide automotive repair services.
 - CAR_RENTAL: Businesses that rent or lease automobiles.
 - TRUCK_SERVICES: Business that sell or service trucks and tractor trailers.
 - HEALTH_CARE: Facilities that include dental offices, hospitals, nursing homes and other health care-related services.
 - GOVERNMENT: A Place where government services are provided.
 - EDUCATION: Facilities that are used for educational purposes including primary schooling, secondary schooling, universities and more.
 - LIBRARY: Facilities that offer books, periodicals, audio, video and other material for public use.
 - EVENTS: An area or facility used for the hosting of fairs and conventions.
 - PARKING: Area or building used for parking cars
 - SPORTS: A facility used for individual and team sports including recreational sports.
 - FACILITIES: Facilities with miscellaneous uses such as Clubhouses, Offices, and Registration Offices.
 - CITY: Represents a named settlement that may be a (large) city, town, or tiny village
 - OUTDOORS_COMPLEX: Outdoor areas or complexes with designations for specific businesses or interests.
 - BUILDING: Areas and buildings designated for residential or office use
 - ADMINISTRATIVE_REGION: An administrative region, such as a postal area, or a named street/square/intersection.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| PlacePlaceCategory | string |  - RESTAURANT: An establishment that prepares and serves refreshments and prepared meals.
 - COFFEE_TEA: An establishment that sells drinks, such as coffee and tea, as well as refreshments.
 - NIGHTLIFE: An establishment that provides evening entertainment and usually serves alcoholic beverages.
 - CINEMA: An establishment that shows movies through screen projection.
 - CULTURE: An establishment where various types of performing arts are presented.
 - GAMBLING_LOTTERY: An establishment that provides gambling entertainment.
 - ATTRACTION: A designated area of special interest to tourists.
 - MUSEUM: An establishment dedicated to the preservation and exhibition of artistic, historical, or scientific artifacts.
 - RELIGIOUS_PLACE: An establishment of special religious significance or where religious services are held.
 - WATER: A natural and geographical feature of the earth's surface that is covered with water, such as a lake, river, stream or ocean.
 - MOUNTAIN: A natural and geographical feature that is higher than the surrounding land.
 - UNDERSEA: Undersea attractions
 - FOREST: A forest, heath or other vegetation
 - GEOGRAPHICAL: Natural and geographical locations
 - AIRPORT: A designated area that serves various aspects of aviation related sports, including gliders, recreational aircraft and model airplanes.
 - PUBLIC_TRANSPORTATION: A facility for travelers who are travelling between stops on public transport.
 - CARGO_TRANSPORTATION: A facility that handles some aspect of the transportation of cargo freight.
 - REST_AREA: An establishment along a motorway (controlled access road) that provides restrooms and parking.
 - HOTEL: A business that provides lodging or temporary living quarters.
 - LODGE: A business that provides lodging to the public generally without room service.
 - OUTDOORS: Public land preserved and maintained for recreational use.
 - LEISURE: A park that contains rides and/or other entertainment which may be based on a central theme.
 - CONVENIENCE_STORE: An establishment that sells groceries, candy, toiletries, soft drinks, tobacco products, newspapers and other products.
 - SHOPPING_CENTER: A complex of businesses that are co-located and share common services.
 - DEPARTMENT_STORE: A business that sells a wide variety of merchandise that is organized by product or service departments.
 - FOOD_AND_DRINKS: A business that sells specialty products of a particular type of food or beverage.
 - PHARMACY: A business that sells medications, toiletry items and other retail cosmetics.
 - ELECTRONICS: A business that sells consumer electronics and electronic entertainment equipment.
 - HARDWARE_HOUSE_GARDEN: A business that sells crafts, gardening, remodeling, or decorating items for the home.
 - BOOKSTORE: A business that sells books, magazines and other reading material.
 - CLOTHING_AND_ACCESSORIES: A business that sells apparel items, garments or fashion accessories for men, women, and children.
 - STORE: A business that sells a variety of products targeted to consumers.
 - HAIR_BEAUTY: A business that provides hair styling and personal appearance services. Places in this category may also sell hair products and other related cosmetic items.
 - BANKING: Businesses that specialize in the maintenance, lending, exchange, or issuance of money.
 - ATM: A computer terminal that allows bank customers to deposit, withdraw, or transfer funds without the assistance of a bank teller.
 - MONEY_SERVICES: Businesses that provide money related services.
 - MEDIA: Businesses that provide communication services.
 - COMMERCIAL_SERVICES: Businesses that provide a service or product for use by other businesses.
 - BUSINESS_INDUSTRY: Businesses that employ people in and around the city in which it is located.
 - EMERGANCY_SERVICES: Municipal emergency services
 - CONSUMER_SERVICES: An organization that provides consumer services for a variety of products for used by the public.
 - POST_OFFICE: An office or station that receives, sorts, dispatches and delivers mail to a specific area or region.
 - TOOURIST_INFORMATION: Businesses that provide a variety of information for visiting tourists, such as event schedules, lodging/accommodations, restaurants, attractions and more
 - FEUL_STATION: Businesses that sell fuel for vehicles
 - CAR_DEALER: Businesses that sell new automobiles and motorcycles.
 - CAR_REPAIR: Businesses that provide automotive repair services.
 - CAR_RENTAL: Businesses that rent or lease automobiles.
 - TRUCK_SERVICES: Business that sell or service trucks and tractor trailers.
 - HEALTH_CARE: Facilities that include dental offices, hospitals, nursing homes and other health care-related services.
 - GOVERNMENT: A Place where government services are provided.
 - EDUCATION: Facilities that are used for educational purposes including primary schooling, secondary schooling, universities and more.
 - LIBRARY: Facilities that offer books, periodicals, audio, video and other material for public use.
 - EVENTS: An area or facility used for the hosting of fairs and conventions.
 - PARKING: Area or building used for parking cars
 - SPORTS: A facility used for individual and team sports including recreational sports.
 - FACILITIES: Facilities with miscellaneous uses such as Clubhouses, Offices, and Registration Offices.
 - CITY: Represents a named settlement that may be a (large) city, town, or tiny village
 - OUTDOORS_COMPLEX: Outdoor areas or complexes with designations for specific businesses or interests.
 - BUILDING: Areas and buildings designated for residential or office use
 - ADMINISTRATIVE_REGION: An administrative region, such as a postal area, or a named street/square/intersection. |  |

### PublicTransportRouteLegPublicTransportMode

 - UNKNOWN_PUBLIC_TRANSPORT_MODE: Unknown.
 - HIGH_SPEED_TRAIN: High-speed train.
 - INTERCITY_TRAIN: Intercity/Euro-City train.
 - INTER_REGIONAL_TRAIN: Inter-regional or fast train.
 - REGIONAL_TRAIN: Regional train.
 - CITY_TRAIN: City train.
 - BUS: Bus.
 - FERRY: Boat or ferry.
 - SUBWAY: Subway/metro train.
 - LIGHT_RAIL: Tram.
 - PRIVATE_BUS: Privately-ordered bus or taxi.
 - INCLINED: Inclined tram/funicular.
 - AERIAL: Cable car.
 - BUS_RAPID: Rapid bus.
 - MONORAIL: Monorail.
 - WALK: Walking.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| PublicTransportRouteLegPublicTransportMode | string |  - UNKNOWN_PUBLIC_TRANSPORT_MODE: Unknown.
 - HIGH_SPEED_TRAIN: High-speed train.
 - INTERCITY_TRAIN: Intercity/Euro-City train.
 - INTER_REGIONAL_TRAIN: Inter-regional or fast train.
 - REGIONAL_TRAIN: Regional train.
 - CITY_TRAIN: City train.
 - BUS: Bus.
 - FERRY: Boat or ferry.
 - SUBWAY: Subway/metro train.
 - LIGHT_RAIL: Tram.
 - PRIVATE_BUS: Privately-ordered bus or taxi.
 - INCLINED: Inclined tram/funicular.
 - AERIAL: Cable car.
 - BUS_RAPID: Rapid bus.
 - MONORAIL: Monorail.
 - WALK: Walking. |  |

### RideOfferCancellationPolicy

- UNKNOWN_CANCEL_POLICY: Unknown cancellation policy.
 - ALLOWED: Cancellation by the client is allowed.
 - NOT_ALLOWED: Cancellation by the client is not allowed.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| RideOfferCancellationPolicy | string | - UNKNOWN_CANCEL_POLICY: Unknown cancellation policy.
 - ALLOWED: Cancellation by the client is allowed.
 - NOT_ALLOWED: Cancellation by the client is not allowed. |  |

### RideOfferTransitType

 - UNKNOWN_TRANSIT_TYPE: Unknown transit type.
 - TAXI: Taxi ride
 - PUBLIC_TRANSPORT: Public transport ride.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| RideOfferTransitType | string |  - UNKNOWN_TRANSIT_TYPE: Unknown transit type.
 - TAXI: Taxi ride
 - PUBLIC_TRANSPORT: Public transport ride. |  |

### RideQueryRideStatusFilter

 - UNKNOWN_RIDE_STATUS_FILTER: Unknown ride status.
 - PAST: Terminated rides (includes the statuses: COMPLETED, REJECTED or CANCELLED). Default: in the past 14 days.
 - FUTURE: Pre-booked rides in status PROCESSING or ACCEPTED. Default: in the past 180 days.
 - ONGOING: Ongoing rides (all rides other than PAST and FUTURE). Default: in the past 3 hours.
 - ALL: All rides.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| RideQueryRideStatusFilter | string |  - UNKNOWN_RIDE_STATUS_FILTER: Unknown ride status.
 - PAST: Terminated rides (includes the statuses: COMPLETED, REJECTED or CANCELLED). Default: in the past 14 days.
 - FUTURE: Pre-booked rides in status PROCESSING or ACCEPTED. Default: in the past 180 days.
 - ONGOING: Ongoing rides (all rides other than PAST and FUTURE). Default: in the past 3 hours.
 - ALL: All rides. |  |

### RideStatusUpdateStatusReasonCode

 - UNKNOWN_STATUS_REASON: no specific reason.
 - REJECTED_PAYMENT_TECHNICAL_ERROR: technical error during payment.
 - REJECTED_PAYMENT_REJECTED_PAY_METHOD: the bank rejected the pay method. Example - the credit card is expired.
 - REJECTED_PAYMENT_REJECTED_TRANSACTION: the bank rejected the transaction for some reason.
 - REJECTED_SUPPLIER_DECLINED: the supplier declined the request.
 - REJECTED_OFFER_EXPIRED: the offer is expired.
 - REJECTED_OTHER: rejected because of another technical reason.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| RideStatusUpdateStatusReasonCode | string |  - UNKNOWN_STATUS_REASON: no specific reason.
 - REJECTED_PAYMENT_TECHNICAL_ERROR: technical error during payment.
 - REJECTED_PAYMENT_REJECTED_PAY_METHOD: the bank rejected the pay method. Example - the credit card is expired.
 - REJECTED_PAYMENT_REJECTED_TRANSACTION: the bank rejected the transaction for some reason.
 - REJECTED_SUPPLIER_DECLINED: the supplier declined the request.
 - REJECTED_OFFER_EXPIRED: the offer is expired.
 - REJECTED_OTHER: rejected because of another technical reason. |  |

### VehicleVehicleType

 - STANDARD: Standard vehicle.
 - LIMO: Limousine.
 - VAN: Van.
 - OTHER: Other vehicle.
 - NOT_SUPPLIED: Vehicle type not supplied.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| VehicleVehicleType | string |  - STANDARD: Standard vehicle.
 - LIMO: Limousine.
 - VAN: Van.
 - OTHER: Other vehicle.
 - NOT_SUPPLIED: Vehicle type not supplied. |  |

### commonAddress

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| country | string | Localized country name. | No |
| country_code | string | ISO 3166-alpha-3 country code. | No |
| state | string | State (first subdivision level below the country, if relevant). | No |
| county | string | County (second subdivision level below the country, if relevant). | No |
| city | string | City/town. | No |
| district | string | District (subdivision level below the city). | No |
| sub_district | string | Sub-district (subdivision level below the district; e.g. commonly used in IND). | No |
| street | string | Street name. | No |
| house_number | string | House number; depending on regional characteristics, can also be house name. | No |
| postal_code | string | Postal code (zipcode). | No |
| building | string | Building name; e.g. commonly used in HKG. | No |
| line | [ string ] | Formatted address lines. | No |

### commonBookingConstraints

* A structure for defining the number of passengers and special requirements for the ride.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| passengers_no | long | The number of passengers (1 or more). | No |
| suitcases_no | long | The number of suitcases (0 or more). | No |

### commonCancellationInfo

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| cancelling_party | [CancellationInfoParty](#cancellationinfoparty) | Which party canceled the ride. | No |
| cancel_reason | string | The reason the ride was canceled (a free-text string). | No |
| request_time_ms | string (uint64) | The time the cancellation was requested. | No |
| status | [commonCancellationInfoStatus](#commoncancellationinfostatus) | The status of the cancellation request. | No |
| cancel_reason_category | [CancellationInfoCancelReasonCategory](#cancellationinfocancelreasoncategory) | The cancellation reason cateory. | No |
| status_reason | [CancellationInfoStatusReason](#cancellationinfostatusreason) | The reason for the cancellation status (e.g. why it was rejected). | No |

### commonCancellationInfoStatus

 - UNKNOWN_STATUS: The cancellation status is unknown.
 - PROCESSING: The cancellation request is being processed.
 - ACCEPTED: The cancellation request is accepted.
 - REJECTED: The cancellation request is rejected.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| commonCancellationInfoStatus | string |  - UNKNOWN_STATUS: The cancellation status is unknown.
 - PROCESSING: The cancellation request is being processed.
 - ACCEPTED: The cancellation request is accepted.
 - REJECTED: The cancellation request is rejected. |  |

### commonCreditCard

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| last_4_digits | string |  | No |
| brand | [commonCreditCardBrand](#commoncreditcardbrand) |  | No |
| holder_name | string |  | No |

### commonCreditCardBrand

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| commonCreditCardBrand | string |  |  |

### commonDemandCancellingParty

- UNKNOWN: The cancelling party is unknown.
 - DEMANDER: The demander cancelled the ride (e.g. concierge).
 - PASSENGER: The passenger cancelled the ride.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| commonDemandCancellingParty | string | - UNKNOWN: The cancelling party is unknown.
 - DEMANDER: The demander cancelled the ride (e.g. concierge).
 - PASSENGER: The passenger cancelled the ride. |  |

### commonDriverDetails

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| name | string | The driver’s first and last name. | No |
| phone_number | string | The driver’s telephone number. | No |
| photo_url | string | A URL pointing to the driver’s photo. This is mandatory in some countries. | No |
| driving_license_id | string | The driver’s driving license ID. This is mandatory in some countries. | No |

### commonEmpty

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| commonEmpty | object |  |  |

### commonFare

* here mobility fare. Required for generating receipts and invoices.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| items | [ [FareFareItem](#farefareitem) ] |  | No |
| currency_code | string |  | No |

### commonPassengerCancelReasonCategory

- UNKNOWN_PASSENGER_CANCEL_REASON_CATEGORY: Unknown cancellation category.
 - DRIVER_NO_SHOW: Driver did not show up.
 - PRICE_CHANGED: Ride price changed.
 - ETA_CHANGED: Ride ETA changed.
 - UNSUITABLE_VEHICLE: Ride vehicle is not suitable.
 - DRIVER_BEHAVED_INAPPROPRIATELY: Driver behaved inappropriately.
 - CHANGED_MY_PLANS: Passenger changed plans.
 - OTHER_PASSENGER_CANCEL_REASON_CATEGORY: Other.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| commonPassengerCancelReasonCategory | string | - UNKNOWN_PASSENGER_CANCEL_REASON_CATEGORY: Unknown cancellation category.
 - DRIVER_NO_SHOW: Driver did not show up.
 - PRICE_CHANGED: Ride price changed.
 - ETA_CHANGED: Ride ETA changed.
 - UNSUITABLE_VEHICLE: Ride vehicle is not suitable.
 - DRIVER_BEHAVED_INAPPROPRIATELY: Driver behaved inappropriately.
 - CHANGED_MY_PLANS: Passenger changed plans.
 - OTHER_PASSENGER_CANCEL_REASON_CATEGORY: Other. |  |

### commonPassengerDetails

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| name | string | Mandatory. The passenger’s first and last name. | No |
| phone_number | string | Mandatory. The passenger’s telephone number. | No |
| photo_url | string | Optional. A URL pointing to the passenger’s photo. | No |
| email | string | Optional. The passenger's email address. | No |

### commonPayMethod

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| card | [commonCreditCard](#commoncreditcard) |  | No |
| type | [commonPayMethodType](#commonpaymethodtype) |  | No |

### commonPayMethodType

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| commonPayMethodType | string |  |  |

### commonPaymentFlow

- OFFLINE_PAYMENT: Offline flow
 - ONLINE_PAYMENT: Online flow

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| commonPaymentFlow | string | - OFFLINE_PAYMENT: Offline flow
 - ONLINE_PAYMENT: Online flow |  |

### commonPaymentFlowFilter

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| commonPaymentFlowFilter | string |  |  |

### commonPaymentFlowSet

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| offline_payment | boolean (boolean) |  | No |
| online_payment | boolean (boolean) |  | No |

### commonPlace

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| name | string | The place name. | No |
| category | [PlacePlaceCategory](#placeplacecategory) | The place category (e.g.: Airport, Restaurant, Park, etc.). | No |

### commonPoint

* A point in the world, expressed as a {latitude, longitude) pair. Latitude values range from -180 to 180.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| lat | double | Latitude. | No |
| lng | double | Longitude. | No |

### commonPrice

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| amount | string | The price’s numeric amount in decimal format. For example "12.5", "12", etc. Unsigned. | No |
| currency_code | string | The price currency. An ISO 4217 Currency Code, for example: "USD", "EUR", "JPY". | No |

### commonPriceEstimate

* A price estimate for a ride. Contains only one field value: either a fixed price, or a price range.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| fixed | [commonPrice](#commonprice) | A single fixed price amount. | No |
| range | [commonPriceRange](#commonpricerange) | Lower and upper limits of a price range. | No |

### commonPriceRange

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| lower_bound | string | The range’s lower limit, for example: "12.5", "12", etc. Unsigned. | No |
| upper_bound | string | The range’s upper limit, for example: "12.5", "12", etc. Unsigned. | No |
| currency_code | string | The price currency. An ISO 4217 Currency Code, for example: "USD", "EUR", "JPY". | No |

### commonPublicTransportRouteLeg

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| mode | [PublicTransportRouteLegPublicTransportMode](#publictransportroutelegpublictransportmode) | Type of transportation for the leg. | No |
| duration_ms | string (uint64) | Duration of the leg in milliseconds. | No |
| distance_meters | long | Distance of the leg in meters. | No |
| line | string | Name of the line of this public transportation (if relevant). | No |
| origin | [v2commonLocation](#v2commonlocation) | Origin location of the leg. | No |
| departure_time_ms | string (uint64) | Time of departure from the start of the leg in milliseconds. | No |
| destination | [v2commonLocation](#v2commonlocation) | Destination location of the leg. | No |
| arrival_time_ms | string (uint64) | Time of arrival from the start of the leg in milliseconds. | No |
| operator | string | Name of the public transportation operator for this leg. | No |

### commonRide

*
A ride with a specific supplier. This entity contains relatively static info: driver, vehicle, passengers etc.
The more dynamic info of the ride, including its progress along the route, is in the entity Ride.

Below is the lifecycle of the ride:

PROCESSING [initial status of the ride after CreateRide(), lasting 0-15 sec.]
PROCESSING --> ACCEPTED [For a pre-booked ride, this status will be active until 30min before the ride.]
PROCESSING --> REJECTED [The ride has been rejected. Terminal state.]
ACCEPTED --> PROCESSING [This transition occurs if the supplier cancels a pre-booked ride, and the Marketplace tries to book a new ride.]
ACCEPTED --> ((NORMAL FLOW)) --> COMPLETE [The ride has been completed. Terminal state.]

The typical flow is: DRIVER_ASSIGNED --> DRIVER_EN_ROUTE --> AT_PICKUP --> PASSENGER_ON_BOARD --> AT_DROPOFF

CANCELLED [Terminal state. Can be reached from any other state, if a demander or supplier cancels the ride.]

NOTE: Once a ride reaches a terminal state, it cannot transition to any other state.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| user_id | string | The ID of the user who created this ride. | No |
| ride_id | string | A unique ride id. | No |
| route | [commonRoute](#commonroute) | The ride route as confirmed by the marketplace and the supplier. | No |
| prebook_pickup_time_ms | string (uint64) | Optional. For a pre-booked ride, contains the requested pickup time. | No |
| booking_estimated_price | [commonPriceEstimate](#commonpriceestimate) | Optional. The estimated price at the time of booking. | No |
| constraints | [commonBookingConstraints](#commonbookingconstraints) | Constraints defined at the time of booking, such as number of passengers and suitcases. | No |
| status_log | [commonRideStatusLog](#commonridestatuslog) | The ride’s current status, and status history. | No |
| supplier | [commonSupplier](#commonsupplier) | Supplier details. | No |
| passenger | [commonPassengerDetails](#commonpassengerdetails) | The passenger details at the time of ride creation. | No |
| passenger_note | string | Optional. A note added by the passenger at the time of ride creation. Can include additional information about the pickup or other special requests. | No |
| driver | [commonDriverDetails](#commondriverdetails) | Optional. This field is only filled when the ride status changes to DRIVER_ASSIGNED and after. | No |
| vehicle | [commonVehicle](#commonvehicle) | Optional. This field is only filled when the ride status changes to DRIVER_ASSIGNED and after. | No |
| cancellation_policy | [RideOfferCancellationPolicy](#rideoffercancellationpolicy) | The cancellation policy for the ride. | No |
| cancellation_info | [commonCancellationInfo](#commoncancellationinfo) | Optional. When a cancellation occurs, this field contains information about the cancellation. | No |
| cancellation_request_received_but_not_allowed | boolean (boolean) | When a cancellation occurs, this field value is TRUE if cancellation isn't allowed. | No |
| price | [commonPrice](#commonprice) | Optional. The price of the ride updated by the supplier. | No |
| app_id | string | Optional. The ID of the app. | No |
| confirmed_pickup_point | [commonPoint](#commonpoint) |  | No |
| payment_flow | [commonPaymentFlow](#commonpaymentflow) | The payment flow in this ride. | No |
| requested_route | [commonRoute](#commonroute) | The ride route as the user requested. | No |

### commonRideLocation

* Provides the real-time location and progress of the vehicle. Updated every ~10 seconds.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| ride_id | string | The ID of the ride. | No |
| vehicle_location | [commonPoint](#commonpoint) | Optional. The current location of the vehicle. | No |
| estimated_pickup_time_ms | string (uint64) | Optional. The estimated time (in epoch) of pickup, constantly updated until the vehicle is at the pickup location.
This field will be deprecated soon, please use estimated_pickup_time_seconds instead. | No |
| estimated_dropoff_time_ms | string (uint64) | Optional. The estimated time (in epoch) of drop-off, constantly updated until the vehicle is at the drop-off location.
This field will be deprecated soon, please use estimated_dropoff_time_seconds instead. | No |
| last_update_time_ms | string (uint64) | The last time this entity is updated. Used for tracking updates. | No |
| estimated_pickup_time_seconds | [protobufUInt32Value](#protobufuint32value) |  | No |
| estimated_dropoff_time_seconds | [protobufUInt32Value](#protobufuint32value) |  | No |

### commonRideOffer

* An offer for a ride on the given route.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| offer_id | string | A unique offer ID. If this offer is chosen, the client sends this ID when calling CreateRide. | No |
| supplier | [commonSupplier](#commonsupplier) | The supplier details. | No |
| route | [commonRoute](#commonroute) | The ride route as confirmed by the marketplace and the supplier. | No |
| estimated_pickup_time_ms | string (uint64) | Optional. Pickup time (in epoch) estimate sent by the supplier.
NOTE: This field will be deprecated soon, please use estimated_pickup_time_seconds instead. | No |
| estimated_dropoff_time_ms | string (uint64) | Optional. Drop-off time (in epoch) estimate sent by the supplier.
NOTE: This field will be deprecated soon, please use estimated_ride_duration_seconds instead. | No |
| price_estimation | [commonPriceEstimate](#commonpriceestimate) | Optional. A price estimate for the ride. | No |
| offer_expiration_time_ms | string (uint64) | The offer expiration time (in milliseconds from the time the offer is sent). | No |
| cancellation_policy | [RideOfferCancellationPolicy](#rideoffercancellationpolicy) | The cancellation policy of the supplier (cancellation allowed or not allowed). | No |
| duration_ms | string (uint64) | Duration of the route in milliseconds.
NOTE: this field will be deprecated soon. Please use duration_seconds instead. | No |
| transfers | long | Number of transport changes to reach the destination. | No |
| legs | [ [commonPublicTransportRouteLeg](#commonpublictransportrouteleg) ] | A list of transportation legs for the route, if this offer is a public transportation offer. | No |
| transit_type | [RideOfferTransitType](#rideoffertransittype) | Specifies the transit type of this offer. | No |
| estimated_pickup_time_seconds | [protobufUInt32Value](#protobufuint32value) |  | No |
| estimated_ride_duration_seconds | [protobufUInt32Value](#protobufuint32value) | Optional. Estimated number of seconds between pickup and dropoff.
NOTE: It does not include the time until pickup. | No |
| duration_seconds | string (uint64) | Duration of the route in seconds.
NOTE: this field will be deprecated soon. Please use estimated_ride_duration_seconds instead. | No |
| supported_payment_flows | [commonPaymentFlowSet](#commonpaymentflowset) | Optional. Supported payment methods. | No |
| requested_route | [commonRoute](#commonroute) | The ride route as the user requested. | No |

### commonRideOfferSortType

- BY_PRICE: Sort by price (lowest price first).
 - BY_ETA: Sort by arrival time (earliest arrival time first).

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| commonRideOfferSortType | string | - BY_PRICE: Sort by price (lowest price first).
 - BY_ETA: Sort by arrival time (earliest arrival time first). |  |

### commonRideOffersResponse

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| offers | [ [commonRideOffer](#commonrideoffer) ] | A list of ride offers. | No |

### commonRidePayment

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| ride_id | string |  | No |
| status | [commonRidePaymentStatus](#commonridepaymentstatus) |  | No |
| pay_method | [commonPayMethod](#commonpaymethod) |  | No |
| final_price | [commonPrice](#commonprice) |  | No |
| fare | [commonFare](#commonfare) |  | No |

### commonRidePaymentStatus

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| commonRidePaymentStatus | string |  |  |

### commonRidePreferences

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| subscribe_to_messages | boolean (boolean) | Optional. Specifies if messages about the ride will be sent to the passenger. Default is false. | No |
| messages_locale | string |  | No |

### commonRideQuery

* A query for a list of rides matching the query filters. Used as parameter for GetRides(), which supports pagination, sorting and filtering.

To fetch the next page of results, copy the pagination field from the response to the RideQuery.from_time_ms field:
next_request.from_time_ms = response.to_time_ms

Paging can be used in 2 ways: ENDLESS PAGING and SINGLE SNAPSHOT.

ENDLESS PAGING - relevant to ascending sort orders.
In this mode, the client calls GetRides() at regular intervals to receive new or updated records.

Use the sort order UPDATE_TIME_ASC to receive all changes on rides.
Use the sort order CREATE_TIME_ASC to receive each ride exactly once (without updates).
Use the sort order PICKUP_TIME_ASC to query for future rides.

SINGLE SNAPSHOT - in this mode, the client wants to fetch all the rides currently available, and needs to know what is the last page.
To identify the last page, set the 'limit' field in the RideQuery, and check if the amount of rides in the result
is lower than the limit. By default any result with less than 200 rides is the last page.

NOTE:
- When the sort is by CREATE_TIME (asc or desc), rides never repeat between pages.
- When the sort is by UPDATE_TIME (asc or desc), rides in previous pages can appear again (because of updates).
- When the sort is by PICKUP_TIME (asc or desc), rides in previous pages can appear again, but rarely.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| from_time_ms | string (uint64) | Optional. Filters rides according to update or creation time (depending on the sort type).
When the sort is UPDATE_TIME_ASC, returns rides UPDATED AFTER this time.
When the sort is UPDATE_TIME_DESC, returns rides UPDATED BEFORE this time.
When the sort is CREATE_TIME_ASC, returns rides CREATED AFTER this time.
When the sort is CREATE_TIME_DESC, return rides CREATED BEFORE this time.

Default value for ascending sort orders is NOW-3 hours, expect for FUTURE or PAST rides.
Default value for FUTURE rides is Now-180 days.
Default value for PAST rides is NOW-14 days.
Default value for descending sort orders is NOW.
This value is in UTC (milliseconds since Epoch time). | No |
| limit | long | Optional. The maximal number of rides to return. When not set, the default is 200. | No |
| status_filter | [RideQueryRideStatusFilter](#ridequeryridestatusfilter) | Optional. Return only rides with the given status. When not set, rides with all statuses are returned. | No |
| sort_by | [commonRideQuerySortType](#commonridequerysorttype) | Optional. Default is UPDATE_TIME_ASC. | No |

### commonRideQueryResponse

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| rides | [ [commonRide](#commonride) ] | The list of rides that matched the query. | No |
| from_time_ms | string (uint64) | The earliest update time in this result set. The lowest possible value is current time minus 3 hours.
This value is in UTC, in milliseconds since Epoch time. | No |
| to_time_ms | string (uint64) | A time "cursor" for pagination. Contains the last time in the result set, ordered by the sort type.
To get the next page, pass this value to the next call for GetRides() to field RideQuery.from_time_ms
This value is in UTC, in milliseconds since Epoch time. | No |

### commonRideQuerySortType

 - UNKNOWN_SORT_TYPE: Unknown sort order.
 - UPDATE_TIME_ASC: Ascending order of update time.
 - UPDATE_TIME_DESC: Descending order of update time.
 - CREATE_TIME_ASC: Ascending order of creation time.
 - CREATE_TIME_DESC: Descending order of creation time.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| commonRideQuerySortType | string |  - UNKNOWN_SORT_TYPE: Unknown sort order.
 - UPDATE_TIME_ASC: Ascending order of update time.
 - UPDATE_TIME_DESC: Descending order of update time.
 - CREATE_TIME_ASC: Ascending order of creation time.
 - CREATE_TIME_DESC: Descending order of creation time. |  |

### commonRideStatusLog

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| last_update_time_ms | string (uint64) | The last time this entity was updated. Used for tracking updates. | No |
| create_time_ms | string (uint64) | The time the booking was created. | No |
| closed_time_ms | string (uint64) | Optional. If relevant, the time the ride was closed (reached a terminal state). | No |
| is_ride_location_available | boolean (boolean) | If this value is TRUE, you can retrieve live updates on the ride’s location by calling GetRideLocation (during statuses DRIVER_ASSIGNED to COMPLETED). | No |
| current_status | [commonRideStatusUpdateStatus](#commonridestatusupdatestatus) | The ride’s current status. | No |
| prev_statuses | [ [commonRideStatusUpdate](#commonridestatusupdate) ] | A list of previous ride statuses, ordered by their timestamp values. | No |
| current_status_reason_code | [RideStatusUpdateStatusReasonCode](#ridestatusupdatestatusreasoncode) | the status reasons - describes WHY did we change the status to this one. | No |

### commonRideStatusUpdate

* A ride status update, and the time it occurred. Used in the status log.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | [commonRideStatusUpdateStatus](#commonridestatusupdatestatus) | The new ride status. | No |
| timestamp_ms | string (uint64) | The time the ride status changed (UNIX Epoch time in milliseconds). | No |
| status_reason_code | [RideStatusUpdateStatusReasonCode](#ridestatusupdatestatusreasoncode) |  | No |

### commonRideStatusUpdateStatus

- UNKNOWN: Unknown.
 - PROCESSING: Looking for a supplier.
 - REJECTED: The supplier cannot fulfill the request. Terminal state.
 - ACCEPTED: A supplier accepted the ride, but a driver is not yet assigned. For a pre-booked ride, this state may last a long while.
 - DRIVER_ASSIGNED: Driver and vehicle are assigned to the ride.
 - DRIVER_EN_ROUTE: Vehicle on its way to pickup.
 - AT_PICKUP: Vehicle at pickup.
 - PASSENGER_ON_BOARD: Vehicle on the way, and passenger on board.
 - AT_DROPOFF: Vehicle arrived at drop-off.
 - COMPLETED: Ride finished successfully. Terminal state.
 - CANCELLED: Ride cancelled by supplier or demander. Terminal state.
 - FAILURE: Ride closed after a duration with no updates.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| commonRideStatusUpdateStatus | string | - UNKNOWN: Unknown.
 - PROCESSING: Looking for a supplier.
 - REJECTED: The supplier cannot fulfill the request. Terminal state.
 - ACCEPTED: A supplier accepted the ride, but a driver is not yet assigned. For a pre-booked ride, this state may last a long while.
 - DRIVER_ASSIGNED: Driver and vehicle are assigned to the ride.
 - DRIVER_EN_ROUTE: Vehicle on its way to pickup.
 - AT_PICKUP: Vehicle at pickup.
 - PASSENGER_ON_BOARD: Vehicle on the way, and passenger on board.
 - AT_DROPOFF: Vehicle arrived at drop-off.
 - COMPLETED: Ride finished successfully. Terminal state.
 - CANCELLED: Ride cancelled by supplier or demander. Terminal state.
 - FAILURE: Ride closed after a duration with no updates. |  |

### commonRideTrackingDetails

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| ride_tracking_id | string | The ride tracking ID. | No |
| status_log | [commonRideStatusLog](#commonridestatuslog) | The tracked ride ride status log.
Note: this field will be deprectaed soon, please use the ride object instead. | No |
| driver | [commonDriverDetails](#commondriverdetails) | The ride's driver details.
Note: this field will be deprectaed soon, please use the ride object instead. | No |
| vehicle | [commonVehicle](#commonvehicle) | The ride's vehicle details.
Note: this field will be deprectaed soon, please use the ride object instead. | No |
| supplier | [commonSupplier](#commonsupplier) | The ride's supplier details.
Note: this field will be deprectaed soon, please use the ride object instead. | No |
| location_and_eta | [commonRideLocation](#commonridelocation) | The ride's location and ETA. | No |
| cancellation_info | [commonCancellationInfo](#commoncancellationinfo) | When cancellation occurs, this field contains information about the cancellation.
Note: this field will be deprectaed soon, please use the ride object instead. | No |
| ride | [commonRide](#commonride) | The ride object. | No |

### commonRoute

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| pickup | [v2commonLocation](#v2commonlocation) | Mandatory. The route’s pickup location. | No |
| destination | [v2commonLocation](#v2commonlocation) | Mandatory. The route’s destination location. | No |

### commonSupplier

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| supplier_id | string | A unique supplier ID. | No |
| english_name | string | The name of the supplier, in English. | No |
| local_name | string | Optional. The name of the supplier in the local language. | No |
| logo_url | string | Optional. A URL pointing to a logo image for the supplier. | No |
| phone_number | string | The supplier’s telephone number. | No |
| address | string | The supplier’s address. | No |
| supplier_notes | [ string ] | The supplier's notes. | No |

### commonTransitOptions

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| max_transfers | integer | Optional. Maximum number of changes or transfers allowed in a route. Default is unlimited. Range is 0-6. | No |
| max_walking_distance_meters | integer | Optional. Specifies a maximum walking distance in meters. Default is 2000. Range is 0-6000. | No |
| locale | string |  | No |

### commonTransportTypePreference

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| use_taxi | boolean (boolean) |  | No |
| use_public_transport | boolean (boolean) |  | No |

### commonVehicle

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| license_plate_number | string | The vehicle’s license plate number. | No |
| vehicle_type | [VehicleVehicleType](#vehiclevehicletype) | The vehicle type (standard, limo, van). | No |
| make | string | The vehicle make. | No |
| model | string | The vehicle model. | No |
| color | string | The vehicle color. | No |
| vehicle_id | string | Optional. This number helps passenger identify the car as it appears on car "hat" (Sign) or written somewhere on the car. | No |

### commonVerticalsCoverageResponse

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| verticals | [ [RideOfferTransitType](#rideoffertransittype) ] |  | No |

### protobufUInt32Value

Wrapper message for `uint32`.

The JSON representation for `UInt32Value` is JSON number.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| value | long | The uint32 value. | No |

### s2sCancelRideRequest

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| ride_id | string | Mandatory. The unique ride ID. | No |
| user_id | string | Optional. The ID of the requesting user. | No |
| cancel_reason | string | Optional. Free text. The reason for the cancellation. | No |
| cancel_reason_category | [commonPassengerCancelReasonCategory](#commonpassengercancelreasoncategory) | Optional. The category of the cancellation. | No |
| cancelling_party | [commonDemandCancellingParty](#commondemandcancellingparty) | Optional. The party cancelling the ride - demander or passenger. Default is passenger. | No |

### s2sCancelTrackedRideRequest

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| ride_tracking_id | string | Mandatory. The ID from the ride tracker url. | No |
| passenger_phone | string | Mandatory. the passenger phone for validation purposes.
Note: This field will be deprecated soon. | No |
| cancel_reason | string | Optional. Free text. The reason for the cancellation. | No |
| cancel_reason_category | [commonPassengerCancelReasonCategory](#commonpassengercancelreasoncategory) | Optional. The category of the cancellation. | No |

### s2sCreatePublicTransportRideRequest

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| user_id | string | Mandatory. The user ID for which the ride is created. | No |
| offer_id | string | Mandatory. An offer ID that was returned by GetRideOffers(). | No |
| passenger | [commonPassengerDetails](#commonpassengerdetails) | Mandatory. The passenger details at the time of booking. | No |
| preferences | [commonRidePreferences](#commonridepreferences) | Optional. Preferences for the ride
NOTE: this field is not yet supported. | No |

### s2sCreateRideRequest

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| user_id | string | Mandatory. The user ID for which the ride is created. | No |
| offer_id | string | Mandatory. An offer ID that was returned by GetRideOffers(). | No |
| passenger | [commonPassengerDetails](#commonpassengerdetails) | Mandatory. The passenger details at the time of booking. | No |
| subscribe_to_messages | boolean (boolean) | DEPRECATED. Please use the RidePreferences object to specify messaging preferences. | No |
| preferences | [commonRidePreferences](#commonridepreferences) | Optional. Preferences for the ride. | No |
| payment_ticket_id | string | Optional. Ticket to be used for online payment. | No |

### v2commonLocation

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| point | [commonPoint](#commonpoint) | Geo-location (latitude and longitude). | No |
| address | [commonAddress](#commonaddress) | Street address. | No |
| free_text | string | Optional. Street address in a free text format. | No |
| place | [commonPlace](#commonplace) | Optional. Place information of the location. | No |