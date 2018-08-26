marketplace/public/grpc/demand_handler/v2/demand_c2s_service.proto-REST
=======================================================================
**Version:** version not set

### /demand.v2.c2s/offers
---
##### ***GET***
**Summary:** *  Get ride offers based on a ride request. May take a few seconds. When no offers are available, returns an empty response.
Errors:
INVALID_ARGUMENT: Invalid field value. For example: prebook_pickup_time is in the past, route.pickup.lat is not a valid latitude, etc.

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
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
| route.pickup.free_text | query | Place name or street address in a free text format. | No | string |
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
| route.destination.free_text | query | Place name or street address in a free text format. | No | string |
| constraints.passengers_no | query | The number of passengers (1 or more). | No | long |
| constraints.suitcases_no | query | The number of suitcases (0 or more). | No | long |
| prebook_pickup_time_ms | query | FUTURE FEATURE, CURRENTLY UNSUPPORTED: Optional. A future pickup time, which is at least 30 minutes after the request time. An empty value indicates a request for an immediate ride. | No | string (uint64) |
| price_range.lower_bound | query | The range’s lower limit, for example: "12.5", "12", etc. Unsigned. | No | string |
| price_range.upper_bound | query | The range’s upper limit, for example: "12.5", "12", etc. Unsigned. | No | string |
| price_range.currency_code | query | The price currency. An ISO 4217 Currency Code, for example: "USD", "EUR", "JPY". | No | string |
| sort_type | query | FUTURE FEATURE, CURRENTLY UNSUPPORTED: Optional. How to sort the RideOffers, by price or by ETA. (The Marketplace default sort order is by best price, and then minimal ETA.).   - BY_PRICE: Sort by price (lowest price first).  - BY_ETA: Sort by arrival time (earliest arrival time first). | No | string |
| passenger_note | query | Optional. A free text note from the passenger. | No | string |
| transit_options.max_transfers | query | Optional. Maximum number of changes or transfers allowed in a route. Default is unlimited. Range is 0-6. | No | integer |
| transit_options.max_walking_distance_meters | query | Optional. Specifies a maximum walking distance in meters. Default is 2000. Range is 0-6000. | No | integer |
| transit_options.locale | query | Optional. The client's locale. Complies with the ISO 639-1 standard and defaults to en. | No | string |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonRideOffersResponse](#commonrideoffersresponse) |

### /demand.v2.c2s/publictransport
---
##### ***POST***
**Summary:** Notify the marketplace that a public transportation offer was chosen

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body |  | Yes | [c2sCreatePublicTransportRideRequest](#c2screatepublictransportriderequest) |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonEmpty](#commonempty) |

### /demand.v2.c2s/rides
---
##### ***GET***
**Summary:** * Get rides for the current user.
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
| body | body |  | Yes | [c2sCreateRideRequest](#c2screateriderequest) |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonRide](#commonride) |

### /demand.v2.c2s/rides/{ride_id}
---
##### ***GET***
**Summary:** * Get a ride by ID. Use this call to poll for the ride status (every 10 seconds).
NOTE: The status of closed rides (COMPLETED, CANCELLED, REJECTED) never changes.
Errors:
NOT_FOUND: Ride does not exist

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| ride_id | path |  | Yes | string |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonRide](#commonride) |

### /demand.v2.c2s/rides/{ride_id}/cancel
---
##### ***PUT***
**Summary:** * Cancel a ride. Returns immediately without waiting for a response from the supplier.
Errors:
NOT_FOUND: Ride does not exist
FAILED_PRECONDITION: Cancel is not allowed by policy, or because the status is REJECTED, COMPLETED, or CANCELLED.

**Parameters**

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| ride_id | path |  | Yes | string |
| body | body |  | Yes | [c2sCancelRideRequest](#c2scancelriderequest) |

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonEmpty](#commonempty) |

### /demand.v2.c2s/rides/{ride_id}/location
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

**Responses**

| Code | Description | Schema |
| ---- | ----------- | ------ |
| 200 |  | [commonRideLocation](#commonridelocation) |

### /demand.v2.c2s/verticalscoverage
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

### CancellationInfoParty

 - UNKNOWN: The cancelling party is unknown.
 - DEMANDER: The client cancelled the ride.
 - SUPPLIER: The supplier cancelled the ride.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| CancellationInfoParty | string |  - UNKNOWN: The cancelling party is unknown.
 - DEMANDER: The client cancelled the ride.
 - SUPPLIER: The supplier cancelled the ride. |  |

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

### c2sCancelRideRequest

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| ride_id | string | Mandatory. The unique ride ID. | No |
| cancel_reason | string | Optional. Free text. The reason for the cancellation. | No |

### c2sCreatePublicTransportRideRequest

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| offer_id | string | Mandatory. An offer ID that was returned by GetRideOffers(). | No |
| passenger | [commonPassengerDetails](#commonpassengerdetails) | Mandatory. The passenger details at the time of booking. | No |
| preferences | [commonRidePreferences](#commonridepreferences) | Optional. Preferences for the ride.
NOTE: this field is not yet supported. | No |

### c2sCreateRideRequest

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| offer_id | string | Mandatory. An offer ID that was returned by GetRideOffers(). | No |
| passenger | [commonPassengerDetails](#commonpassengerdetails) | Mandatory. The passenger details at the time of booking. | No |
| subscribe_to_messages | boolean (boolean) | DEPRECATED. Please use the RidePreferences object to specify messaging preferences. | No |
| preferences | [commonRidePreferences](#commonridepreferences) | Optional. Preferences for the ride. | No |

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

### commonPassengerDetails

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| name | string | Mandatory. The passenger’s first and last name. | No |
| phone_number | string | The passenger’s telephone number. | No |
| photo_url | string | Optional. A URL pointing to the passenger’s photo. | No |
| email | string | Optional. The passenger's email address. | No |

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

* A ride with a specific supplier. This entity contains relatively static info: driver, vehicle, passengers etc.
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
| route | [commonRoute](#commonroute) | The ride route. | No |
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
| confirmed_pickup_point | [commonPoint](#commonpoint) | Optional. The ride confirmed pickup point calculated by Here-API. | No |

### commonRideLocation

* Provides the real-time location and progress of the vehicle. Updated every ~10 seconds.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| ride_id | string | The ID of the ride. | No |
| vehicle_location | [commonPoint](#commonpoint) | Optional. The current location of the vehicle. | No |
| estimated_pickup_time_ms | string (uint64) | Optional. The estimated time of pickup, constantly updated until the vehicle is at the pickup location.
This field will be deprecated soon, please use estimated_pickup_time_seconds instead. | No |
| estimated_dropoff_time_ms | string (uint64) | Optional. The estimated time of drop-off, constantly updated until the vehicle is at the drop-off location.
This field will be deprecated soon, please use estimated_dropoff_time_seconds instead. | No |
| last_update_time_ms | string (uint64) | The last time this entity is updated. Used for tracking updates. | No |
| estimated_pickup_time_seconds | [protobufUInt32Value](#protobufuint32value) | Pickup time estimate sent by the supplier. | No |
| estimated_dropoff_time_seconds | [protobufUInt32Value](#protobufuint32value) | Drop-off time estimate sent by the supplier or calculated by Marketplace. | No |

### commonRideOffer

* An offer for a ride on the given route.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| offer_id | string | A unique offer ID. If this offer is chosen, the client sends this ID when calling CreateRide. | No |
| supplier | [commonSupplier](#commonsupplier) | The supplier details. | No |
| route | [commonRoute](#commonroute) | The ride route that the supplier suggests. | No |
| estimated_pickup_time_ms | string (uint64) | Optional. Pickup time estimate sent by the supplier.
NOTE: This field will be deprecated soon, please use estimated_pickup_time_seconds instead. | No |
| estimated_dropoff_time_ms | string (uint64) | Optional. Drop-off time estimate sent by the supplier.
NOTE: This field will be deprecated soon, please use estimated_ride_duration_seconds instead. | No |
| price_estimation | [commonPriceEstimate](#commonpriceestimate) | Optional. A price estimate for the ride. | No |
| offer_expiration_time_ms | string (uint64) | The offer expiration time (in milliseconds from the time the offer is sent). | No |
| cancellation_policy | [RideOfferCancellationPolicy](#rideoffercancellationpolicy) | The cancellation policy of the supplier (cancellation allowed or not allowed). | No |
| duration_ms | string (uint64) | Duration of the route in milliseconds.
NOTE: this field will be deprecated soon. Please use duration_seconds instead. | No |
| transfers | long | Number of transport changes to reach the destination. | No |
| legs | [ [commonPublicTransportRouteLeg](#commonpublictransportrouteleg) ] | A list of transportation legs for the route, if this offer is a public transportation offer. | No |
| transit_type | [RideOfferTransitType](#rideoffertransittype) | Specifies the transit type of this offer. | No |
| estimated_pickup_time_seconds | [protobufUInt32Value](#protobufuint32value) | Optional. Pickup time estimate sent by the supplier. | No |
| estimated_ride_duration_seconds | [protobufUInt32Value](#protobufuint32value) | Optional. Drop-off time estimate sent by the supplier or calculated by Marketplace.
This is the time between pickup to dropoff. It does not contain the time to pickup. | No |
| duration_seconds | string (uint64) | Duration of the route in seconds. | No |

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

### commonRidePreferences

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| subscribe_to_messages | boolean (boolean) | Optional. Specifies if messages about the ride will be sent to the passenger. Default is false. | No |

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

### commonRideStatusUpdate

* A ride status update, and the time it occurred. Used in the status log.

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| status | [commonRideStatusUpdateStatus](#commonridestatusupdatestatus) | The new ride status. | No |
| timestamp_ms | string (uint64) | The time the ride status changed (UNIX Epoch time in milliseconds). | No |

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

### commonTransitOptions

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| max_transfers | integer | Optional. Maximum number of changes or transfers allowed in a route. Default is unlimited. Range is 0-6. | No |
| max_walking_distance_meters | integer | Optional. Specifies a maximum walking distance in meters. Default is 2000. Range is 0-6000. | No |
| locale | string | Optional. The client's locale. Complies with the ISO 639-1 standard and defaults to en. | No |

### commonVehicle

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| license_plate_number | string | The vehicle’s license plate number. | No |
| vehicle_type | [VehicleVehicleType](#vehiclevehicletype) | The vehicle type (standard, limo, van). | No |
| make | string | The vehicle make. | No |
| model | string | The vehicle model. | No |
| color | string | The vehicle color. | No |

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

### v2commonLocation

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| point | [commonPoint](#commonpoint) | Geo-location (latitude and longitude). | No |
| address | [commonAddress](#commonaddress) | Street address. | No |
| free_text | string | Place name or street address in a free text format. | No |