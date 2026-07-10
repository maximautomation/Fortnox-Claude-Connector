---
title: "Fortnox API"
source: "https://apps.fortnox.se/apidocs"
author:
published:
created: 2026-07-09
description:
tags:
  - "clippings"
---
Download OpenAPI specification:Download

## Documentation

The Fortnox API is organized around REST. This means that we’ve designed it to have resource-oriented URLs and be as predictable as possible for you as developer.

It also means that we use HTTP status codes when something goes wrong and HTTP verbs understod by many API clients around the web.

We use a modified version of OAuth2 for authentication to offer a secure way for both you and our users to interact.

The API is generally built to support both XML and JSON but in this documentation all the examples will be in JSON.

We encourage you to read all the articles in the [Guides & Good to Know section](https://www.fortnox.se/developer/guides-and-good-to-know/) first, before going forward and learning about the different resources.

This to ensure you get an understanding of some of the shared components of the API such as parameters and error handling.

## Rate limits

The limit per access-token is 25 requests per 5 seconds. This equals to 300 requests per minute.

[Read more about this here.](https://www.fortnox.se/developer/guides-and-good-to-know/rate-limits-for-fortnox-api/)

## Query parameters

Use query parameters with the?-character and separate parameters with the &-character.

**Example:** GET - [https://api.fortnox.se/3/invoices?accountnumberfrom=3000&accountnumberto=4000](https://api.fortnox.se/3/invoices?accountnumberfrom=3000&accountnumberto=4000) Read more about our parameters [here](https://www.fortnox.se/developer/guides-and-good-to-know/parameters/)

Search the documentation using the search field in the top left corner.

## Integration Ratings

Get ratings data

## Users

Resource for retrieving active users of an integration

Prerequisites The partner has an active developer account and a published integration that is purchased through Fortnox.

## Fetch user information for a single published integration and tenant

##### path Parameters

| integrationId  required | integer \<int64> |
| --- | --- |
| tenantId  required | integer \<int64> |

### Responses

### Response samples

## Custom Document Type

Handles types for custom documents.

A custom document is identified by its type and id. Each type belongs to a category, either INBOUND or OUTBOUND.

Note that custom document types are created automatically if necessary when you create custom documents.

The following `referenceTypes` are not allowed for custom document types. Variants of these containing dashes, underscores, lower case, upper case etc are not allowed either.

- ARTICLEPRODUCTION
- ARTIKELPRODUKTION
- CUSTOMERINVOICE
- CUSTOMERORDER
- DELIVERYNOTE
- FAKTURA
- FÖLJESEDEL
- INGÅENDESALDO
- INKÖP
- INKÖPSORDER
- INVENTERING
- INVENTORY
- INVOICE
- ITEMPRODUCTION
- KREDITFAKTURA
- KREDITORDER
- KUNDFAKTURA
- KUNDORDER
- LAGERFLYTT
- LEGACYINTEGRATIONIN
- LEGACYINTEGRATIONOUT
- LEVERANTÖRSFAKTURA
- LEVFAKTURA
- MANUALDELIVERY
- MANUALINBOUND
- MANUALINBOUNDDELIVERY
- MANUALOUTBOUND
- MANUALOUTBOUNDDELIVERY
- MANUELLINLEVERANS
- MANUELLLEVERANS
- MANUELLUTLEVERANS
- NEGATIVEOPENINGBALANCES
- NEGATIVTINGÅENDESALDO
- ORDER
- PLOCKLISTA
- POSITIVEOPENINGBALANCES
- PRODUCTION
- PRODUKTION
- PURCHASE
- PURCHASEORDER
- STOCKTAKING
- STOCKTAKINGDEVIATION
- STOCKTRANSFER
- SUPINVOICE
- SUPPLIERINVOICE

## Create custom document type

Create type, if it doesn't already exists. Note that new custom document types are created automatically when you create custom documents, so normally you do not need to call this method.

Throws HTTP 400 `referenceTypeNotAllowed` if the name of the type is not allowed.

##### Request Body schema: application/json

The `CustomDocumentType`.

| category  required | string  Enum: "INBOUND" "OUTBOUND" |
| --- | --- |
| referenceType  required | string \[ 1.. 25 \] characters \[a-zA-Z0-9\_-\]+ |

### Responses

### Request samples

### Response samples

## Get custom document type

##### path Parameters

| type  required | string  the name of the reference type |
| --- | --- |

### Responses

### Response samples

## Custom Inbound Document

Handles Custom Inbound Documents.

A Custom Inbound Document is an externally created document for registering inbound deliveries to warehouse.

## Get custom inbound document

##### path Parameters

| type  required | string  Document type. |
| --- | --- |
| id  required | string  Document id. |

### Responses

### Response samples

## Save custom inbound document

##### path Parameters

| type  required | string  min 1 character, max 25 characters, may contain letters A-Z, digits 0-9, underscore (\_), and dash (-), type is case-insensitive  > ``` > Type is a custom name/reference of the document that will be used to reference the document type  >  > * If type is not known, it will be registered as belonging to the INBOUND category.  >  > * If type is an existing custom document type of category OUTBOUND an error is thrown.  >  > * If type is invalid an error is thrown. > ``` |
| --- | --- |
| id  required | string  min 1 character, max 25 characters, may only contain digits 0-9 |

##### Request Body schema: application/json

the `CustomInboundDocument` to create

| currency | object (warehouse\_Currency) |
| --- | --- |
| date  required | string \<date> |
| id | string \[ 1.. 25 \] characters ^\[0-9\]+ |
| note | string <= 1000 characters |
| rows  required | Array of objects (warehouse\_CustomInboundDocumentRow) |
| type | string \[ 1.. 25 \] characters \[a-zA-Z0-9\_-\]+ |
| voided | boolean |
| warehouseReady | boolean |

### Responses

### Request samples

### Response samples

## Release custom inbound document

The document will be locked and bookkept. The inbound deliveries will affect available stock.

##### path Parameters

| type  required | string  document type |
| --- | --- |
| id  required | string  document id |

### Responses

### Response samples

## Void custom inbound document

Voiding a document will undo the possible stock changes that the document had made, note that the document and the transactions created are not deleted. Some limitations apply, see below.

##### path Parameters

| type  required | string  document type |
| --- | --- |
| id  required | string  document id |

##### query Parameters

| force | boolean  true if the document should be voided even if the document has connected outbounds, defaults to false. |
| --- | --- |

### Responses

### Response samples

## Custom Outbound Document

Handles Custom Outbound Documents.

A Custom Outbound Document is an externally created document for registering outbound deliveries to warehouse.

## Get custom outbound document

##### path Parameters

| type  required | string  document type |
| --- | --- |
| id  required | string  document id |

### Responses

### Response samples

## Save a custom outbound document

If type is not known, it will be registered as belonging to the OUTBOUND category.  
If type is an existing custom document type of category INBOUND an error is thrown.  
If type is invalid an error is thrown.

##### path Parameters

| type  required | string  the type of the custom outbound document, min 1 character, max 25 characters, may contain letters A-Z, digits 0-9, underscore (\_), and dash (-). Always stored as upper case. |
| --- | --- |
| id  required | string  the id of the custom outbound document, min 1 character, max 25 characters, may only contain digits 0-9 |

##### Request Body schema: application/json

the `CustomOutboundDocument` to create

| averageCosts | Array of objects (warehouse\_AverageCost) |
| --- | --- |
| date  required | string \<date> |
| deliveryState  required | string  Enum: "registration" "reservation" "delivery" |
| forcedDelivery | boolean |
| id | string \[ 1.. 25 \] characters ^\[0-9\]+ |
| note | string <= 1000 characters |
| referenceType | string \[ 1.. 25 \] characters \[a-zA-Z0-9\_-\]+ |
| rows  required | Array of objects (warehouse\_CustomOutboundDocumentRow) |
| voided | boolean |
| warehouseReady | boolean |

### Responses

### Request samples

### Response samples

## Release custom outbound document

##### path Parameters

| type  required | string  document type |
| --- | --- |
| id  required | string  document id |

### Responses

### Response samples

## Void custom outbound document

##### path Parameters

| type  required | string  document type |
| --- | --- |
| id  required | string  document id |

##### query Parameters

| force | boolean  true if the document should be voided even if the document has connected outbounds, defaults to false. |
| --- | --- |

### Responses

### Response samples

## Incoming Goods

General resource for incoming goods.

## List Incoming Goods Documents

List incoming goods documents matching the given parameters.

Sortable fields: `id`, `has_delivery_note`, `delivery_note_id`, `supplier_number`, `date`

##### query Parameters

| released | boolean  `true` to include only released documents. `false` to include only non-released documents. |
| --- | --- |
| completed | boolean  `true` to include only completed documents. `false` to include only non-completed documents. |
| voided | boolean  `true` to include only voided documents. `false` to include only non-voided documents. |
| supplierNumber | string  Include only documents with the given `supplierNumber`. |
| itemId | string  Include only documents with the given `itemId`. |
| note | string  Include only documents where `note` -field contains the given text (case-insensitive). |
| deliveryNote | string  Include only documents where `deliveryNote` -field contains the given text (case-insensitive). |
| q | string  Include only documents where `id` or `deliveryNote` -field contains the given text (case-insensitive). |

### Responses

### Response samples

## Create Incoming Goods document

##### Request Body schema: \*/\*

The `IncomingGoods` document.

| completed | boolean |
| --- | --- |
| costCenterCode | string |
| date | string \<date> |
| deliveryNoteId  required | string \[ 1.. 50 \] characters |
| hasDeliveryNote | boolean |
| id | integer \<int64> |
| note | string <= 1000 characters |
| projectId | string |
| released | boolean |
| rows | Array of objects (warehouse\_IncomingGoodsRow) |
| stockPointCode | string |
| stockPointId | string \<uuid> |
| stockPointName | string |
| supplierName | string <= 1024 characters |
| supplierNumber | string <= 1024 characters |
| voided | boolean |

### Responses

### Response samples

## Get Incoming Goods document

##### path Parameters

| id  required | integer \<int64>  Incoming goods document id. |
| --- | --- |

##### query Parameters

| ignoreSupplierInvoiceId | integer \<int64>  This Supplier Invoice id will be excluded when calculating the takenQuantity. |
| --- | --- |

### Responses

### Response samples

## Partial update Incoming Goods document

Perform a partial update of an `IncomingGoods` document. The partial update will update `note`, `deliveryNoteId`, `supplierName` and `hasDeliveryNote` It is possible to perform a partial update of a released/completed (TODO:?) document.

##### path Parameters

| id  required | integer \<int64>  Incoming goods document id. |
| --- | --- |

##### Request Body schema: \*/\*

the incoming goods document to update. The partial update updates `note`, `deliveryNoteId`, `supplierName` and `hasDeliveryNote`

| completed | boolean |
| --- | --- |
| costCenterCode | string |
| date | string \<date> |
| deliveryNoteId  required | string \[ 1.. 50 \] characters |
| hasDeliveryNote | boolean |
| id | integer \<int64> |
| note | string <= 1000 characters |
| projectId | string |
| released | boolean |
| rows | Array of objects (warehouse\_IncomingGoodsRow) |
| stockPointCode | string |
| stockPointId | string \<uuid> |
| stockPointName | string |
| supplierName | string <= 1024 characters |
| supplierNumber | string <= 1024 characters |
| voided | boolean |

### Responses

### Response samples

## Update Incoming Goods document

##### path Parameters

| id  required | integer \<int64>  Incoming goods document id. |
| --- | --- |

##### Request Body schema: \*/\*

The `IncomingGoods` document.

| completed | boolean |
| --- | --- |
| costCenterCode | string |
| date | string \<date> |
| deliveryNoteId  required | string \[ 1.. 50 \] characters |
| hasDeliveryNote | boolean |
| id | integer \<int64> |
| note | string <= 1000 characters |
| projectId | string |
| released | boolean |
| rows | Array of objects (warehouse\_IncomingGoodsRow) |
| stockPointCode | string |
| stockPointId | string \<uuid> |
| stockPointName | string |
| supplierName | string <= 1024 characters |
| supplierNumber | string <= 1024 characters |
| voided | boolean |

### Responses

### Response samples

## Complete Incoming Goods document

Mark a released Incoming Goods document as Completed. Bookkeeping will be finalized. A Completed Incoming Goods document cannot be matched against any more Supplier Invoices.

##### path Parameters

| id  required | integer \<int64>  Incoming goods document id. |
| --- | --- |

##### Request Body schema: \*/\*

Date for bookkeeping in format `"YYYY-MM-DD"`. Must be between document's release date (inclusive) and today's date (inclusive).

string

### Responses

### Response samples

## Release Incoming Goods document

The document will be locked and bookkept. The inbound deliveries will affect available stock.

##### path Parameters

| id  required | integer \<int64>  Incoming goods document id. |
| --- | --- |

### Responses

### Response samples

## Void Incoming Goods document

Void a document. If an Incoming Goods document has been Completed, or matched against Supplier Invoice, it cannot be voided.

##### path Parameters

| id  required | integer \<int64>  Incoming goods document id. |
| --- | --- |

### Responses

### Response samples

## Manual Document

Handles listing of `ManualDocument` s.

There are three types of Manual Documents in Warehouse:

- Manual Inbound Documents,
- Manual Outbound Documents, and
- Stock Transfer Documents

## List manual documents

##### query Parameters

| state | string  Enum: "all" "unreleased" "released" "voided"  Include only documents with given state. |
| --- | --- |
| type | string  Enum: "all" "inbound" "outbound" "stocktransfer"  Include only documents with given type. |
| itemId | string  Include only documents containing the given item. |

### Responses

### Response samples

## Manual Inbound Document

Handles `ManualInboundDocument` s

## Create manual inbound document

The `id` is set automatically.

##### Request Body schema: application/json

manual inbound document

| currency  required | string = 3 characters |
| --- | --- |
| currencyRate  required | number >= 0.000001 |
| currencyUnit | integer \<int32> >= 1 |
| date  required | string \<date> |
| id | integer \<int64> |
| note | string <= 1000 characters |
| released | boolean |
| rows  required | Array of objects (warehouse\_ManualInboundDocumentRow) \[ 1.. 2147483647 \] items |
| stockPointCode | string |
| stockPointId | string \<uuid> |
| stockPointName | string |
| voided | boolean |

### Responses

### Request samples

### Response samples

## Get manual inbound document

##### path Parameters

| id  required | integer \<int64>  Manual Inbound document id. |
| --- | --- |

### Responses

### Response samples

## Update note on manual inbound document

When a Manual Inbound has been released, it is locked. The `note` field can still be updated using this endpoint.

##### path Parameters

| id  required | integer \<int64>  Manual Inbound document id. |
| --- | --- |

##### Request Body schema: application/json

Note.

| note | string <= 1000 characters |
| --- | --- |

### Responses

### Request samples

### Response samples

## Update manual inbound document

##### path Parameters

| id  required | integer \<int64>  Manual Inbound document id. |
| --- | --- |

##### Request Body schema: application/json

Manual Inbound document

| currency  required | string = 3 characters |
| --- | --- |
| currencyRate  required | number >= 0.000001 |
| currencyUnit | integer \<int32> >= 1 |
| date  required | string \<date> |
| id | integer \<int64> |
| note | string <= 1000 characters |
| released | boolean |
| rows  required | Array of objects (warehouse\_ManualInboundDocumentRow) \[ 1.. 2147483647 \] items |
| stockPointCode | string |
| stockPointId | string \<uuid> |
| stockPointName | string |
| voided | boolean |

### Responses

### Request samples

### Response samples

## Release manual inbound document

The document will be locked and bookkept.

The following error codes might be thrown:

cannot\_release\_later\_than\_current\_date

Document date cannot be in the future.

document\_is\_voided

Document is voided.

period\_locked

Document date is within a locked bookkeeping period.

##### path Parameters

| id  required | integer \<int64>  Manual Inbound document id. |
| --- | --- |

### Responses

### Response samples

## Void manual inbound document

A released manual inbound document might have connected outbounds, and can only be force voided. Note that a force void operation might cause a negative stock.

The following error codes might be thrown:

void\_linked\_outbound

If this document has any outbounds transactions connected to it.

##### path Parameters

| id  required | integer \<int64>  Manual Inbound document id. |
| --- | --- |

##### query Parameters

| force | boolean  true if we should force void, defaults to false |
| --- | --- |
| customVoidDate | string \<date>  date the void operation should be bookkeept on |

### Responses

### Response samples

## Manual Outbound Document

Handles `ManualOutboundDocument` s

## Create manual outbound document

The `id` is set automatically.

##### Request Body schema: application/json

manual outbound document

| date  required | string \<date> |
| --- | --- |
| id | integer \<int64> |
| note | string <= 1000 characters |
| released | boolean |
| rows  required | Array of objects (warehouse\_ManualOutboundDocumentRow) <= 2147483647 items |
| stockPointCode | string |
| stockPointId | string \<uuid> |
| stockPointName | string |
| voided | boolean |

### Responses

### Request samples

### Response samples

## Get manual outbound document

##### path Parameters

| id  required | integer \<int64>  Manual Outbound document id. |
| --- | --- |

### Responses

### Response samples

## Update note on manual outbound document

When a Manual Outbound has been released, it is locked. The `note` field can still be updated using this endpoint.

##### path Parameters

| id  required | integer \<int64>  Manual Outbound document id |
| --- | --- |

##### Request Body schema: application/json

Note.

| note | string <= 1000 characters |
| --- | --- |

### Responses

### Request samples

### Response samples

## Update manual outbound document

HTTP code 400 cannot\_modify\_released\_document HTTP code 400 document\_is\_voided Document is voided. HTTP code 404 not found

##### path Parameters

| id  required | integer \<int64>  Manual Outbound document id. |
| --- | --- |

##### Request Body schema: application/json

Manual Outbound document.

| date  required | string \<date> |
| --- | --- |
| id | integer \<int64> |
| note | string <= 1000 characters |
| released | boolean |
| rows  required | Array of objects (warehouse\_ManualOutboundDocumentRow) <= 2147483647 items |
| stockPointCode | string |
| stockPointId | string \<uuid> |
| stockPointName | string |
| voided | boolean |

### Responses

### Request samples

### Response samples

## Release manual outbound document

The document will be locked and bookkept.

The following error codes might be thrown:

cannot\_release\_later\_than\_current\_date

Document date cannot be in the future.

document\_is\_voided

Document is voided.

period\_locked

Document date is within a locked bookkeeping period.

##### path Parameters

| id  required | integer \<int64>  Manual Outbound document id. |
| --- | --- |

### Responses

### Response samples

## Void manual outbound document

##### path Parameters

| id  required | integer \<int64>  Manual Outbound document id. |
| --- | --- |

##### query Parameters

| customVoidDate | string \<date>  if provided this date will be used as the voided date instead of the document date |
| --- | --- |

### Responses

### Response samples

## Production Order

Handles Production Orders.

## List production orders

##### query Parameters

| state | string  Enum: "all" "incomplete" "delayed" "completed" "voided"  Include only production orders with the given state. Allowed states: all, incomplete, delayed, completed, voided. (Default is incomplete) |
| --- | --- |
| itemId | string  Include only production orders with the given production item. |

### Responses

### Response samples

## Create a new production order

Set `itemId` to the item to be produced.

Set `quantity` to number of units to produce.

Set `startDate` to production start state.

ProductionState is set to `reserved` by default. It can also be `registered`. Then no reservations will be made (no quantities will be assigned to the `packageItems` yet).

Setting `outboundStockPointId` (where the `packageItems` will be taken from), and `inboundStockPointId` (where the produced item will be put) is mandatory multiple stockpoints has been activated in the warehouse settings.

Before the document is released, the `productionDate` must be set.

The `packageItems` to include is easiest to get by calling the method `getRequiredProductionParts`.

##### Request Body schema: \*/\*

the production order to create `ProductionOrder`

| batch | string |
| --- | --- |
| costCenterCode | string |
| documentState | string  Enum: "completed" "voided" |
| id | integer \<int64> |
| inboundStockLocationId | string \<uuid> |
| inboundStockPointId | string \<uuid> |
| itemDescription | string |
| itemId | string |
| itemUnit | string |
| note | string <= 1000 characters |
| outboundStockPointId | string \<uuid> |
| packageItems | Array of objects (warehouse\_PackageItem) |
| productionDate | string \<date> |
| productionState  required | string  Enum: "registered" "reserved" "ongoing" |
| projectId | string |
| quantity  required | number >= 0.01 |
| startDate  required | string \<date> |

### Responses

### Response samples

## Get the package items (Bill Of Materials, BOMs) for a production article

If no parameters are supplied, the `totalQuantityRequired` for producing 1 unit is returned.

Query parameter `quantity` can optionally be supplied, which will calculate `totalQuantityRequired`.

If query parameter `id` is supplied, it will get the quantity from that Production Order (the `quantity` query parameter is ignored if `id` is included).

##### path Parameters

| itemId  required | string  Production Article id |
| --- | --- |

##### query Parameters

| id | integer \<int64>  the id of the production order (optional) |
| --- | --- |
| quantity | string  the quantity of the production order (assumed 1 if left empty) |

### Responses

### Response samples

## Release a production order document

The document will be locked and bookkept.

The following error codes might be thrown:

PRODUCTION\_DATE\_IS\_EMPTY

Production date cannot be empty.

CANNOT\_RELEASE\_AFTER\_CURRENT\_DATE

Document date cannot be in the future.

DOCUMENT\_IS\_VOIDED

The document has been voided and can no longer be modified.

DOCUMENT\_IS\_RELEASED

The document has already been released and can no longer be modified.

DOCUMENT\_NOT\_FULLY\_RESERVED

The documents package items (BOMs, Bill Of Materials) has not been fully reserved (reserved quantity is not equal to total required quantity for one or more package item).

##### path Parameters

| id  required | integer \<int64>  Production Order document id. |
| --- | --- |

### Responses

### Response samples

## Void a production order

A released production order might have connected outbounds, and can only be force voided. Note that a force void operation might cause a negative stock.

##### path Parameters

| id  required | integer \<int64>  Production Order document id. |
| --- | --- |

##### query Parameters

| force | boolean  true to force void a released document, default false |
| --- | --- |

### Responses

### Response samples

## Get Production Order document

##### path Parameters

| id  required | integer \<int64>  Production Order document id. |
| --- | --- |

### Responses

### Response samples

## Update the note of a production order

When a Production Order has been released it is locked. However, the `note` field can still be updated using this endpoint.

##### path Parameters

| id  required | integer \<int64>  Production Order document id. |
| --- | --- |

##### Request Body schema: \*/\*

contains data to be patched onto the production order

| note | string <= 1000 characters |
| --- | --- |

### Responses

### Response samples

## Update a production order

Note that you must submit the full Production Order document when updating.

##### path Parameters

| id  required | integer \<int64>  Production Order document id. |
| --- | --- |

##### Request Body schema: \*/\*

the production order data see `ProductionOrder`

| batch | string |
| --- | --- |
| costCenterCode | string |
| documentState | string  Enum: "completed" "voided" |
| id | integer \<int64> |
| inboundStockLocationId | string \<uuid> |
| inboundStockPointId | string \<uuid> |
| itemDescription | string |
| itemId | string |
| itemUnit | string |
| note | string <= 1000 characters |
| outboundStockPointId | string \<uuid> |
| packageItems | Array of objects (warehouse\_PackageItem) |
| productionDate | string \<date> |
| productionState  required | string  Enum: "registered" "reserved" "ongoing" |
| projectId | string |
| quantity  required | number >= 0.01 |
| startDate  required | string \<date> |

### Responses

### Response samples

## Purchase Order

Handles Purchase Orders

## List Purchase Orders

List purchase orders matching the given parameters.

Sortable fields: `id`, `supplier_number`, `order_date`, `internal_reference`, `response_state`, `delivery_date`

##### query Parameters

| q | string  Include only documents where `id` or `internalReference` -field contains the given text (case-insensitive). |
| --- | --- |
| supplierNumber | string  Include only documents with the given `supplierNumber`. |
| state | string  Enum: "NOT\_SENT" "SENT" "SENT\_NOT\_REJECTED" "DELAYED" "RECEIVED" "VOIDED" "CURRENT" "ALL"  Include only documents with the given `purchaseOrderState`. |
| itemId | string  Include only documents with the given `itemId`. |
| purchaseType | string  Enum: "WAREHOUSE" "DROPSHIP"  Include only documents with the given `purchaseType` |
| internalReference | string  Include only documents where \`internalReference' contains the given text (case-insensitive). |
| note | string  Include only documents where `note` -field contains the given text (case-insensitive). |

### Responses

### Response samples

## Create Purchase Order

##### Request Body schema: \*/\*

`PurchaseOrder` document.

| confirmationEmail | string <= 100 characters |
| --- | --- |
| costCenterCode | string <= 25 characters |
| currencyCode  required | string <= 3 characters |
| currencyRate  required | number |
| currencyUnit | integer \<int32> >= 1 |
| customerId | string <= 25 characters |
| customerName | string <= 1024 characters |
| customerNumber | string <= 1024 characters |
| deliveryAddress  required | string \[ 1.. 1024 \] characters |
| deliveryAddress2 | string <= 1024 characters |
| deliveryCity  required | string \[ 1.. 50 \] characters |
| deliveryCountryCode | string <= 3 characters |
| deliveryDate | string \<date> |
| deliveryName  required | string \[ 1.. 50 \] characters |
| deliveryZipCode  required | string \[ 1.. 10 \] characters |
| dropship | boolean |
| id | integer \<int64> |
| internalReference | string <= 50 characters |
| languageCode | string <= 3 characters |
| manuallyCompleted | boolean |
| messageToSupplier | string <= 1000 characters |
| note | string <= 1000 characters |
| orderDate  required | string \<date> |
| orderValue | number |
| orderValueInSEK | number |
| ourReference | string <= 50 characters |
| outboundDocumentReference | object (warehouse\_DocumentReference) |
| paymentTermsCode  required | string <= 20 characters |
| projectId | string <= 25 characters |
| purchaseOrderState | string  Enum: "NOT\_SENT" "SENT" "SENT\_NOT\_REJECTED" "DELAYED" "RECEIVED" "VOIDED" "CURRENT" "ALL" |
| purchaseType | string  Enum: "WAREHOUSE" "DROPSHIP" |
| responseState | string  Enum: "NOT\_SENT" "SENT" "ACCEPTED\_WITH\_REQ\_DLV\_DATE" "ACCEPTED\_WITH\_CHANGED\_DLV\_DATE" "PARTLY\_ACCEPTED\_WITH\_REQ\_DLV\_DATE" "PARTLY\_ACCEPTED\_WITH\_CHANGED\_DLV\_DATE" "REJECTED" |
| rows | Array of objects (warehouse\_PurchaseOrderRow) |
| stockPointCode | string |
| stockPointId | string \<uuid> |
| supplier | string |
| supplierAddress | string <= 1024 characters |
| supplierAddress2 | string <= 1024 characters |
| supplierCity | string <= 1024 characters |
| supplierCountryCode | string <= 3 characters |
| supplierEmail | string <= 100 characters |
| supplierName | string <= 1024 characters |
| supplierNumber  required | string <= 1024 characters |
| supplierPostCode | string <= 1024 characters |
| totalReceivedQuantity | number |
| translatedResponseState | string |
| voided | boolean |
| yourReference | string <= 50 characters |

### Responses

### Response samples

## Get CSV list of Purchase Orders

##### query Parameters

| q | string  Include only documents where `id` or `internalReference` -field contains the given text (case-insensitive). |
| --- | --- |
| supplierNumber | string  Include only documents with the given `supplierNumber`. |
| state | string  Enum: "NOT\_SENT" "SENT" "SENT\_NOT\_REJECTED" "DELAYED" "RECEIVED" "VOIDED" "CURRENT" "ALL"  Include only documents with the given `purchaseOrderState`. |
| itemId | string  Include only documents with the given `itemId`. |
| purchaseType | string  Enum: "WAREHOUSE" "DROPSHIP"  Include only documents with the given `purchaseType` |
| internalReference | string  Include only documents where \`internalReference' contains the given text (case-insensitive). |
| note | string  Include only documents where `note` -field contains the given text (case-insensitive). |
| showPurchaseTypeColumn | boolean  True to include the purchase type column, default is false. |

### Responses

## Update response states

##### query Parameters

| ids | Array of integers \<int64> \[ items \<int64 > \]  List of purchase order ids. |
| --- | --- |

##### Request Body schema: \*/\*

The new response state.

| responseState | string  Enum: "NOT\_SENT" "SENT" "ACCEPTED\_WITH\_REQ\_DLV\_DATE" "ACCEPTED\_WITH\_CHANGED\_DLV\_DATE" "PARTLY\_ACCEPTED\_WITH\_REQ\_DLV\_DATE" "PARTLY\_ACCEPTED\_WITH\_CHANGED\_DLV\_DATE" "REJECTED" |
| --- | --- |

### Responses

### Response samples

## Get Purchase Order

##### path Parameters

| id  required | integer \<int64>  Purchase order id. |
| --- | --- |

##### query Parameters

| ignoreIncomingGoodsId | integer \<int64>  used for calculating the remaining ordered quantity. null will take the received quantity from all incoming goods |
| --- | --- |

### Responses

### Response samples

## Update Purchase Order

##### path Parameters

| id  required | integer \<int64>  Purchase order id. |
| --- | --- |

##### Request Body schema: \*/\*

The `PurchaseOrder` document.

| confirmationEmail | string <= 100 characters |
| --- | --- |
| costCenterCode | string <= 25 characters |
| currencyCode  required | string <= 3 characters |
| currencyRate  required | number |
| currencyUnit | integer \<int32> >= 1 |
| customerId | string <= 25 characters |
| customerName | string <= 1024 characters |
| customerNumber | string <= 1024 characters |
| deliveryAddress  required | string \[ 1.. 1024 \] characters |
| deliveryAddress2 | string <= 1024 characters |
| deliveryCity  required | string \[ 1.. 50 \] characters |
| deliveryCountryCode | string <= 3 characters |
| deliveryDate | string \<date> |
| deliveryName  required | string \[ 1.. 50 \] characters |
| deliveryZipCode  required | string \[ 1.. 10 \] characters |
| dropship | boolean |
| id | integer \<int64> |
| internalReference | string <= 50 characters |
| languageCode | string <= 3 characters |
| manuallyCompleted | boolean |
| messageToSupplier | string <= 1000 characters |
| note | string <= 1000 characters |
| orderDate  required | string \<date> |
| orderValue | number |
| orderValueInSEK | number |
| ourReference | string <= 50 characters |
| outboundDocumentReference | object (warehouse\_DocumentReference) |
| paymentTermsCode  required | string <= 20 characters |
| projectId | string <= 25 characters |
| purchaseOrderState | string  Enum: "NOT\_SENT" "SENT" "SENT\_NOT\_REJECTED" "DELAYED" "RECEIVED" "VOIDED" "CURRENT" "ALL" |
| purchaseType | string  Enum: "WAREHOUSE" "DROPSHIP" |
| responseState | string  Enum: "NOT\_SENT" "SENT" "ACCEPTED\_WITH\_REQ\_DLV\_DATE" "ACCEPTED\_WITH\_CHANGED\_DLV\_DATE" "PARTLY\_ACCEPTED\_WITH\_REQ\_DLV\_DATE" "PARTLY\_ACCEPTED\_WITH\_CHANGED\_DLV\_DATE" "REJECTED" |
| rows | Array of objects (warehouse\_PurchaseOrderRow) |
| stockPointCode | string |
| stockPointId | string \<uuid> |
| supplier | string |
| supplierAddress | string <= 1024 characters |
| supplierAddress2 | string <= 1024 characters |
| supplierCity | string <= 1024 characters |
| supplierCountryCode | string <= 3 characters |
| supplierEmail | string <= 100 characters |
| supplierName | string <= 1024 characters |
| supplierNumber  required | string <= 1024 characters |
| supplierPostCode | string <= 1024 characters |
| totalReceivedQuantity | number |
| translatedResponseState | string |
| voided | boolean |
| yourReference | string <= 50 characters |

### Responses

### Response samples

## Manually complete Purchase Order

The purchase order will be treated as fully received. Any remaining quantity will be ignored.

##### path Parameters

| id  required | integer \<int64>  Purchase order id. |
| --- | --- |

### Responses

### Response samples

## Manually complete dropship order

The dropship order will be treated as fully received. Any remaining quantity will be ignored.

##### path Parameters

| id  required | integer \<int64>  Purchase order id. |
| --- | --- |

### Responses

### Response samples

## List matched documents

Get a list of `DocumentReference` of linked/connected purchase orders to incoming goods and/or invoice document.

##### path Parameters

| id  required | integer \<int64>  Purchase order id. |
| --- | --- |

### Responses

### Response samples

## Get notes

Get notes for a purchase order.

##### path Parameters

| id  required | integer \<int64>  Purchase order id. |
| --- | --- |

### Responses

### Response samples

## Partial update Purchase Order

Perform a partial update of a purchase order, see `PartialPurchaseOrder` for possible fields that are updateable.

##### path Parameters

| id  required | integer \<int64>  Purchase order id. |
| --- | --- |

##### Request Body schema: \*/\*

the changes for the purchase order, see `PartialPurchaseOrder`

| deliveryDate | string \<date> |
| --- | --- |
| internalReference | string <= 50 characters |
| messageToSupplier | string <= 1000 characters |
| note | string <= 1000 characters |
| supplierName | string <= 1024 characters |

### Responses

### Response samples

## Update response state

##### path Parameters

| id  required | integer \<int64>  Purchase order id. |
| --- | --- |

##### Request Body schema: \*/\*

The new response state.

| responseState | string  Enum: "NOT\_SENT" "SENT" "ACCEPTED\_WITH\_REQ\_DLV\_DATE" "ACCEPTED\_WITH\_CHANGED\_DLV\_DATE" "PARTLY\_ACCEPTED\_WITH\_REQ\_DLV\_DATE" "PARTLY\_ACCEPTED\_WITH\_CHANGED\_DLV\_DATE" "REJECTED" |
| --- | --- |

### Responses

### Response samples

## Send purchase order via email

Sends the purchase order with the specified `id` to the recipient and sets the purchase order state to SENT

##### path Parameters

| id  required | integer \<int64>  Purchase order id. |
| --- | --- |

##### Request Body schema: \*/\*

see `PurchaseOrderMailSettings`

| body  required | string |
| --- | --- |
| bodyAsHtml | string |
| receiver  required | string |
| receiverCopy | string |
| receiverSecretCopy | string |
| replyTo  required | string |
| senderName | string |
| subject  required | string |

### Responses

### Response samples

## Void Purchase Order

##### path Parameters

| id  required | integer \<int64>  Purchase order id. |
| --- | --- |

### Responses

### Response samples

## Stock Point

Resource to handle `StockPoint` s.

## List stock points

List stock points, optionally include a query parameter \`q\` to filter on stock point code or name.

Use query param \`state\` to filter on ACTIVE, INACTIVE or ALL (default is to include only ACTIVE stock points).

Stock locations are NOT included in the response.

##### query Parameters

| q | string  filters on stock point code or name. |
| --- | --- |
| state | string  Enum: "ALL" "ACTIVE" "INACTIVE"  filter on stock point state |

### Responses

### Response samples

## Create stock point

Both `code` and `name` are mandatory.

If you want to set a custom delivery address for this stock point, you must remember to set `usingCompanyAddress` to `false`.

Returns 400 `alreadyexists` if a stock point with same code already exists.

Returns 400 `duplicatestocklocations` if two or more stock locations have the same code.

##### Request Body schema: application/json

stock point

| active | boolean |
| --- | --- |
| code  required | string \[ 1.. 10 \] characters |
| deliveryAddress | string <= 50 characters |
| deliveryAddress2 | string <= 50 characters |
| deliveryCity | string <= 50 characters |
| deliveryCountryCode | string <= 3 characters |
| deliveryName | string <= 50 characters |
| deliveryPhone | string <= 50 characters |
| deliveryZipCode | string <= 10 characters |
| id | string \<uuid> |
| name  required | string \[ 1.. 25 \] characters |
| stockLocations | Array of objects (warehouse\_StockLocation) |
| usingCompanyAddress | boolean |

### Responses

### Request samples

### Response samples

## Get stock points

Get stock points by IDs.

Use query param \`state\` to filter on ACTIVE, INACTIVE or ALL (default is to include ALL stock points).

Stock locations are NOT included in the response.

##### query Parameters

| ids | Array of strings \<uuid> \[ items \<uuid > \]  stock point ids (comma separated list of UUIDs) |
| --- | --- |
| state | string  Enum: "ALL" "ACTIVE" "INACTIVE"  filter on `StockPointState`, default is to include ALL stock points. |

### Responses

### Response samples

## Delete stock point

Note that it is not allowed to delete a stock point that is in use.

##### path Parameters

| id  required | string \<uuid>  id |
| --- | --- |

### Responses

### Response samples

## Get stock point

Get stock point by id or code.

##### path Parameters

| id  required | string  stock point code, or stock point id |
| --- | --- |

### Responses

### Response samples

## Append stock locations

Add new stock locations to specific `StockPoint`.

If you include an already existing stock location code, it will be ignored.

##### path Parameters

| id  required | string \<uuid>  stock point id |
| --- | --- |

##### Request Body schema: application/json

A list of `StockLocations` to append.

Array

| code  required | string \[ 1.. 20 \] characters |
| --- | --- |
| id | string \<uuid> |
| name | string <= 25 characters |
| stockPointId | string \<uuid> |

### Responses

### Request samples

### Response samples

## Update stock point

Remember to supply the complete representation of stock point including stock locations.

##### path Parameters

| id  required | string \<uuid>  id |
| --- | --- |

##### Request Body schema: application/json

complete representation of stock point including stock locations.

| active | boolean |
| --- | --- |
| code  required | string \[ 1.. 10 \] characters |
| deliveryAddress | string <= 50 characters |
| deliveryAddress2 | string <= 50 characters |
| deliveryCity | string <= 50 characters |
| deliveryCountryCode | string <= 3 characters |
| deliveryName | string <= 50 characters |
| deliveryPhone | string <= 50 characters |
| deliveryZipCode | string <= 10 characters |
| id | string \<uuid> |
| name  required | string \[ 1.. 25 \] characters |
| stockLocations | Array of objects (warehouse\_StockLocation) |
| usingCompanyAddress | boolean |

### Responses

### Request samples

### Response samples

## Get stock locations

List stock locations for a specific stock point.

Optionally include a query parameter \`q\` to filter on stock location code or name.

##### path Parameters

| id  required | string  stock point id or code |
| --- | --- |

##### query Parameters

| q | string  filters on stock location code or name. |
| --- | --- |

### Responses

### Response samples

## Stock Status

Handles stock status.

## Get stock balance

Get stock balance for each stockpoint.

Returns a list of `itemId`, `stockPointCode`, `availableStock`, `inStock`.

(The difference between `availableStock` and `inStock` is the reserved amount.)

##### query Parameters

| itemIds | Array of strings  Optional filter on itemIds (comma-separated) |
| --- | --- |
| stockPointCodes | Array of strings  Optional filter on stock point codes (comma-separated). |

### Responses

### Response samples

## Stock Taking

Handles stock taking.

A Stock Taking document is created in state "planning". Rows, containing item-stockpoint-stocklocation combinations to be counted, are added to the Stock Taking document.

When the planning is done, the Stock Taking document is updated to state "started", and the stock taking begins.

Setting the stock taken quantity is done by updating the Stock Taking document, and supplying the counted rows. This can be done in "batches", i.e. not all rows needs to be updated at once.

When the stock taking is done, the document is released. The release process will adjust the stock for the stock taking date, and prepare the warehouse bookkeeping data.

## List stock takings

Sortable fields: `id`, `name`, `date`, `responsible`, `state`

##### query Parameters

| state | string  Enum: "all" "planning" "started" "completed" "voided"  Include only stock takings with the given state. |
| --- | --- |
| itemId | string  Include only stock takings with the given item. |

### Responses

### Response samples

## Create stock taking

Create a new Stock Taking document. The only mandatory fields are `name` and `responsible`. `state` will be set to `planning` for a newly created document.

The `date` -field is not mandatory for documents in state `planning`. However, when you update the state to `started` you have to provide a date.

`name` is a descriptive name of the stock taking.

`responsible` is the name of the responsible for the stock taking.

`rows` are added after creation by using the addRows-method.

`projectId` and `costCenterCode` are used for book-keeping, when the Stock Taking document is released.

The field `usingStockPoints` is set from Warehouse system settings upon creation. If multiple stockpoints is used, then the rows will be per item-stockPoint-stockLocation. If multiple stockpoints is NOT used, then the rows will be per item-stockLocation.

##### Request Body schema: \*/\*

stock taking

| costCenterCode | string |
| --- | --- |
| date | string \<date> |
| id | integer \<int64> |
| name  required | string \[ 1.. 50 \] characters |
| projectId | string |
| responsible  required | string \[ 1.. 50 \] characters |
| rows | Array of objects (warehouse\_StockTakingRow) |
| sortParams | object (warehouse\_StockTakingSortParams) |
| sortingId | integer \<int32> |
| state  required | stringplanning\|started\|completed\|voided |
| usingStockPoints | boolean |

### Responses

### Response samples

## Delete Stock Taking document

Permanently deletes a Stock Taking document and its rows.

Only for documents in state `planning` and `started`.

##### path Parameters

| id  required | integer \<int64>  Stock Taking document id. |
| --- | --- |

### Responses

### Response samples

## Get Stock Taking document

##### path Parameters

| id  required | integer \<int64>  Stock Taking document id. |
| --- | --- |

### Responses

### Response samples

## Update a stock taking

Updates can only be done when state is `planning` or `started`.

All updatable fields (`date`, `name`, `responsible`, `state`, `sortingId`, `costCenterCode`, `projectId`) in the document head are set to supplied values.

You cannot set `state` to `completed` or `voided`. Use endpoints release or void for this.

The `date` -field is mandatory for documents in state `started`.

When state is `started` you use this endpoint for setting the stock taken quantity. Only existing rows can be updated - no new rows will be created (use the addRows endpoint for this). Only the supplied rows will be updated. I.e. you don't have to send in **all** document rows - just supply the rows you want to set stockTakenQuantity for. Just make sure to always include all the fields from the document head as mentioned above.

The mandatory fields on the (optionally supplied) rows are: `itemId`, `stockPointId`, `stockLocationId`. Fields `countedBy` and `stockTakenQuantity` are technically not mandatory, but will be set to null if you don't supply them.

##### path Parameters

| id  required | integer \<int64>  Stock Taking document id. |
| --- | --- |

##### Request Body schema: \*/\*

stock taking

| costCenterCode | string |
| --- | --- |
| date | string \<date> |
| id | integer \<int64> |
| name  required | string \[ 1.. 50 \] characters |
| projectId | string |
| responsible  required | string \[ 1.. 50 \] characters |
| rows | Array of objects (warehouse\_StockTakingRow) |
| sortParams | object (warehouse\_StockTakingSortParams) |
| sortingId | integer \<int32> |
| state  required | stringplanning\|started\|completed\|voided |
| usingStockPoints | boolean |

### Responses

### Response samples

## Add rows by filter

Add all matching candidate rows to a stock taking, as specified by filters.

##### path Parameters

| id  required | integer \<int64>  Stock Taking document id. |
| --- | --- |

##### query Parameters

| itemIds | Array of strings |
| --- | --- |
| supplierNumbers | Array of strings |
| stockPointIds | Array of strings |
| stockLocationIds | Array of strings |
| transactionDate | string \<date> |
| itemIdSearch | string |
| itemDescriptionSearch | string |
| excludeZeroBalanceItems | boolean |
| excludeNonInboundItems | boolean |

### Responses

### Response samples

## Get candidate rows

A candidate row is a combination of itemId, stockPointId and stockLocationId that can be added to the Stock Taking document.

Rows already added to the Stock Taking are excluded from this list.

##### path Parameters

| id  required | integer \<int64>  Stock Taking document id. |
| --- | --- |

##### query Parameters

| itemIds | Array of strings |
| --- | --- |
| supplierNumbers | Array of strings |
| stockPointIds | Array of strings |
| stockLocationIds | Array of strings |
| transactionDate | string \<date> |
| itemIdSearch | string |
| itemDescriptionSearch | string |
| excludeZeroBalanceItems | boolean |
| includeNonInboundItems | boolean  Include items that do not exist on inbound deliveries. |

### Responses

### Response samples

## Release Stock Taking document

The document will be locked and bookkept. The Stock Taking document state will be set to `completed`. The stock amount will be adjusted according to the stock taken quantity.

##### path Parameters

| id  required | integer \<int64>  Stock Taking document id. |
| --- | --- |

### Responses

### Response samples

## Delete rows by filter

Remove all rows matching the filter parameters from the Stock Taking document.

##### path Parameters

| id  required | integer \<int64>  Stock Taking document id. |
| --- | --- |

##### query Parameters

| itemIds | Array of strings |
| --- | --- |
| supplierNumbers | Array of strings |
| stockPointIds | Array of strings |
| stockLocationIds | Array of strings |
| transactionDate | string \<date> |
| itemIdSearch | string |
| itemDescriptionSearch | string |
| excludeZeroBalanceItems | boolean |

### Responses

### Response samples

## Get Stock Taking Rows

##### path Parameters

| id  required | integer \<int64>  Stock Taking document id. |
| --- | --- |

##### query Parameters

| itemIds | Array of strings |
| --- | --- |
| supplierNumbers | Array of strings |
| stockPointIds | Array of strings |
| stockLocationIds | Array of strings |
| transactionDate | string \<date> |
| itemIdSearch | string |
| itemDescriptionSearch | string |
| excludeZeroBalanceItems | boolean |
| secondarysortby | string  Secondary sorting column |
| secondaryorder | string  Secondary sorting order |
| stateFilter | string  Enum: "all" "notStockTaken" "stockTakenNoDeviation" "stockTakenWithDeviation" |
| startingRowNo | integer \<int32>  the row number to start the search from, used with startingItemId to jump to specific rows, can be empty |
| startingItemId | string  the itemId that should be on top of the rows list (used to jump to specific row), can be empty |

### Responses

### Response samples

## Add rows

Add rows to a stock taking. If you add an already existing row noting happens.

##### path Parameters

| id  required | integer \<int64>  Stock Taking document id. |
| --- | --- |

##### Request Body schema: \*/\*

A list of `StockTakingRows`.

Array

| countedBy | string <= 100 characters |
| --- | --- |
| currentRowNo | integer \<int32> |
| hasPostReleaseStockChanges | boolean |
| id | string |
| itemId | string <= 50 characters |
| stockLocationId | string \<uuid> |
| stockPointId | string \<uuid> |
| stockTakenQuantity | number |
| stockTakingId | integer \<int64> |
| stockTakingRowId | string |
| totalQuantityInStock | number |

### Responses

### Response samples

## Delete row

Remove single row by id from the Stock Taking document.

##### path Parameters

| id  required | integer \<int64>  Stock Taking document id. |
| --- | --- |
| rowId  required | string  row id |

### Responses

### Response samples

## Void Stock Taking document

Sets the Stock Taking document state to `voided`.

Only documents in state `planning` and `started` can be voided. A `completed` document may not be voided.

##### path Parameters

| id  required | integer \<int64>  Stock Taking document id. |
| --- | --- |

### Responses

### Response samples

## Stock Transfer

Handles `StockTransferDocument` s.

A Stock Transfer moves stock from one location to another. You request a quantity to be moved. The quantity is reserved, and delivered upon release of the Stock Transfer document. The "delivery" makes an inbound delivery to the new location.

## Create a stock transfer document

Outbounds will be reserved in the from-place. Inbounds are created upon release of the stock transfer document.

##### Request Body schema: application/json

stock transfer document

| id | integer \<int64> >= 1 |
| --- | --- |
| note | string <= 1000 characters |
| released | boolean |
| rows  required | Array of objects (warehouse\_StockTransferRow) |
| transferDate | string \<date> |
| version | integer \<int64> |
| voided | boolean |

### Responses

### Request samples

### Response samples

## Get stock transfer document

##### path Parameters

| id  required | integer \<int64>  Stock Transfer document id. |
| --- | --- |

### Responses

### Response samples

## Update a stock transfer document

##### path Parameters

| id  required | integer \<int64>  Stock Transfer document id. |
| --- | --- |

##### Request Body schema: application/json

The `StockTransferDocument` document.

| id | integer \<int64> >= 1 |
| --- | --- |
| note | string <= 1000 characters |
| released | boolean |
| rows  required | Array of objects (warehouse\_StockTransferRow) |
| transferDate | string \<date> |
| version | integer \<int64> |
| voided | boolean |

### Responses

### Request samples

### Response samples

## Release a stock transfer document

This will deliver all outbounds which are reserved in from-place, and create inbounds in the to-place. Nothing happens if you releasr an already released stock transfer document.

Returns `document_is_voided` if document is voided.

##### path Parameters

| id  required | integer \<int64>  Stock Transfer document id. |
| --- | --- |

### Responses

### Response samples

## Void a stock transfer document

Voiding a released stock transfer document is not allowed, and will return `cannot_modify_released_document`

##### path Parameters

| id  required | integer \<int64>  Stock Transfer document id. |
| --- | --- |

##### query Parameters

| force | boolean |
| --- | --- |

### Responses

### Response samples

## Tenant

Return Warehouse activation status for a tenant.

## Articles

Provides information on the status (presence of cost/price) of articles

## Get full article registrations that match filter

**Response property descriptions:**  
***id*** - The unique id of a basic common combination of article registrations. (The basic common combination means "user/purchase date/customer/project/cost center", which leads to a dialog with several article registrations.)  
***purchaseDate*** - The date on which the article is purchased or registered for charging.  
***ownerId*** - The user ID who creates the basic common combination.  
***ownerName*** - The name of the user who creates the basic common combination.  
***version*** - The version of the basic common combination (article dialog) being updated, which is used for handling the concurrency issue.  
***registrationType*** - It is always "ARTICLE" for article list endpoint.  
**Sub-Class - ArticleRegistration:**  
***id*** - The unique id of an article registration.  
***registrationId*** - The id of the basic common combination.  
***orderIndex*** - the order index for the article registration in regard of the common combination.  
***ownerId*** - The user ID who owns the article registration.  
***ownerName*** - The name of the user who owns the article registration.  
***totalQuantity*** - The quantity of the article.  
***unitPrice*** - The unit price connected to the article registration, which might be locked on an invoice/order basis or for non-invoiceable.  
***unitCost*** - The unit cost connected to the article registration, which might be locked on an invoice/order basis.  
***invoiceBasisId*** - The ID of invoice/order basis which is used for creating an invoice/order.  
***nonInvoiceable*** - If the article registration would be ignored for charging or not.  
***note*** - The note on the article registration.  
***documentId*** - The document ID which includes the article registration and is created in Invoicing application.  
***documentType*** - The document type which could be "invoice" or "order".

##### query Parameters

| fromDate | string \<date>  The start date of the search span, the max of which should be 1 year to the end date ("toDate"). Example: 2022-11-01 |
| --- | --- |
| toDate | string \<date>  The end date of the search span, the max of which should be 1 year back to the start date ("fromDate"). Example: 2022-11-30 |
| customerIds | Array of strings  An array of customer IDs which are being used in database and in one-to-one relation with customer numbers. Example: 100,101,102 |
| projectIds | Array of strings  An array of project IDs. Example: p1,p2,p3 |
| includeRegistrationsWithoutProject | boolean  If the article registration without project is included, or not. |
| itemIds | Array of strings  An array of article IDs. Example: s1,s2,s3 |
| costCenterIds | Array of strings  An array of cost center IDs. Example: cc1,cc2,cc3 |
| ownerIds | Array of strings  An array of user ids who own the article registrations. Example: 1,2,3 |
| invoiced | boolean  If a document is created with the article registration, or not. |
| inInvoiceBasis | boolean  If the article registration is locked on an invoice basis, or not. |
| internalArticles | boolean  If the article registration is internal, which is registered on an internal customer, or not. |
| nonInvoiceable | boolean  If the article registration has been moved to non-invoiceable, or not. |
| includeNonInvoiceablePrice | boolean  If the price of the non-invoiceable article registration is included, or not. |

### Responses

### Response samples

## Registrations

## Get time/absence registrations that match filter

**Response property descriptions:**  
***id*** - The unique id of the registration.  
***userId*** - The user ID who owns the registration.  
***userName*** - The name of the user who owns the registration.  
***workedDate*** - The date for which the registration is created.  
***workedHours*** - The time spent, or the time of absence.  
***startTime*** - The start of clock time.  
***stopTime*** - The end of clock time.  
***invoiceText*** - The text to be included in the invoice/order basis which would be used to create an invoice/order.  
***note*** - The note on the registration.  
***chargeHours*** - The time to be invoiced, or 0 for the absence, or locked for non-invoiceable.  
***childId*** - The child ID related to the absence registration of parental leave (FPE), which comes from Payroll application.  
***nonInvoiceable*** - If the registration would be ignored for charging or not.  
***invoiceBasisId*** - The ID of invoice/order basis which is used for creating an invoice/order.  
***documentId*** - The document ID which includes the registration and is created in Invoicing application.  
***documentType*** - The document type which could be "invoice" or "order".  
***unitCost*** - The unit cost from the registration owner who takes the work.  
***unitPrice*** - The unit price for the service on the registration, which comes in priority from "invoice/order basis", "price group" or "service".

##### query Parameters

| fromDate | string \<date>  The start date of the search span, the max of which should be 1 year to the end date ("toDate"). Example: 2022-11-01 |
| --- | --- |
| toDate | string \<date>  The end date of the search span, the max of which should be 1 year back to the start date ("fromDate"). Example: 2022-11-30 |
| customerIds | Array of strings  An array of customer IDs which are being used in database and in one-to-one relation with customer numbers. Example: 100,101,102 |
| projectIds | Array of strings  An array of project IDs. Example: p1,p2,p3 |
| serviceIds | Array of strings  An array of service IDs. Example: s1,s2,s3 |
| costCenterIds | Array of strings  An array of cost center IDs. Example: cc1,cc2,cc3 |
| regCodes | Array of strings  An array of registration codes. Example: TID,SEM,FPE |
| userIds | Array of strings  An array of user IDs that time/absence registrations belong to. Example: 1,2,3 |
| includeRegistrationsWithoutProject | boolean  If the time/absence registration without project is included, or not. |
| invoiced | boolean  If a document is created with the time/absence registration, or not. |
| inInvoiceBasis | boolean  If the time/absence registration is locked on an invoice basis, or not. |
| internalTime | boolean  If the time/absence registration is internal, which is registered on an internal customer, or not. |
| nonInvoiceable | boolean  If the time/absence registration has been moved to non-invoiceable, or not. |
| includeNonInvoiceableChargeHours | boolean  If the price of the non-invoiceable time/absence registration is included, or not. |

### Responses

### Response samples

## Absence Transactions

Absence transaction resources.

| **Code** | **Description** |
| --- | --- |
| ASK | Arbetsskada |
| ATF | Arbetstidsförkortning |
| FPE | Föräldraledig |
| FRA or FR1 | Frånvaro övrigt (FR1 is used in PAXml) |
| HAV | Graviditetspenning |
| KOM | Kompledig |
| MIL | Militärtjänst (max 60 dagar) |
| NAR or NÄR | Närståendevård (NÄR is used in PAXml) |
| OS1 | Sjuk-OB 1 |
| OS2 | Sjuk-OB 2 |
| OS3 | Sjuk-OB 3 |
| OS4 | Sjuk-OB 4 |
| OS5 | Sjuk-OB 5 |
| PAP | Pappadagar |
| PEM | Permission |
| PER | Permitterad |
| SEM | Semester |
| SJK | Sjukfrånvaro |
| SMB | Smittbärare |
| SVE | Svenska för invandrare |
| TJL | Tjänstledig |
| UTB or FAC | Facklig utbildning (FAC is used in PAXml) |
| VAB | Vård av barn |

## Lists all absence transactions

Supports query-string parameters **employeeid** and **date** for filtering the result.

##### query Parameters

| employeeid | string  filter by employee id |
| --- | --- |
| date | string  filter by date |

### Responses

### Response samples

## Create a new absence transaction

Create an absence transaction

##### Request Body schema: \*/\*

Request body for create absence transaction

| AbsenceTransaction | object (fortnox\_Lon\_AbsenceTransactionsSinglePayloadItem) |
| --- | --- |

### Responses

### Response samples

## Delete an absence transaction

Delete an absence transaction

##### path Parameters

| id  required | string \<uuid>  identifies the transaction |
| --- | --- |

### Responses

### Response samples

## Retrieve a specific absence transaction

Retrieves a specific transaction

##### path Parameters

| id  required | string \<uuid>  identifies the transaction |
| --- | --- |

### Responses

### Response samples

## Update a single absence transaction

Update an absence transaction

##### path Parameters

| id  required | string \<uuid>  identifies the transaction |
| --- | --- |

##### Request Body schema: \*/\*

Request body for update absence transaction

| AbsenceTransaction | object (fortnox\_Lon\_AbsenceTransactionsSinglePayloadItem) |
| --- | --- |

### Responses

### Response samples

## Retrieve absence transactions

Retrieves a list of absence transactions for an employee on a specific date and cause code.

##### path Parameters

| id  required | string  identifies the employee |
| --- | --- |
| Date  required | string \<date>  of the absence transaction |
| Code  required | string  Enum: "ASK" "FPE" "FRA" "HAV" "KOM" "MIL" "NAR" "OS1" "OS2" "OS3" "OS4" "OS5" "PAP" "PEM" "PER" "SEM" "SJK" "SMB" "SVE" "TJL" "UTB" "VAB"  status code of the absence transaction |

### Responses

### Response samples

## Account Charts

Account chart resources

## Accounts

Account resources

## List all accounts

The accounts are returned sorted by account number with the lowest number appearing first.

##### query Parameters

| sortby | string  Value: "number"  field to sort returned list on |
| --- | --- |
| lastmodified | string  Lastmodified of accounts to list |
| sru | integer \<int32>  Sru of accounts to list |

### Responses

### Response samples

## Create an account

The created account will be returned if everything succeeded, if there were any problems an error will be returned.

##### query Parameters

| financialyear | integer \<int32>  financial year to create account against |
| --- | --- |

##### Request Body schema: \*/\*

Request body for create account

| Account | object (fortnox\_Bf\_AccountSinglePayloadItem) |
| --- | --- |

### Responses

### Response samples

## Deletes an account

Deletes the specified account in the users current year

##### path Parameters

| Number  required | integer \<int32>  account to delete |
| --- | --- |

### Responses

### Response samples

## Retrieve an account

Retrieves the details of an account. You need to supply the unique account number that was returned when the account was created or retrieved from the list of accounts.

##### path Parameters

| Number  required | integer \<int32>  identifies the account |
| --- | --- |

### Responses

### Response samples

## Update an account

Updates the specified account with the values provided in the properties. Any property not provided will be left unchanged. Note that even though the account number is writeable you can´t change the number of an existing account.

##### path Parameters

| Number  required | integer \<int32>  identifies the account |
| --- | --- |

##### query Parameters

| financialyear | integer \<int32>  financial year to update account against |
| --- | --- |

##### Request Body schema: \*/\*

Request body for update account

| Account | object (fortnox\_Bf\_AccountSinglePayloadItem) |
| --- | --- |

### Responses

### Response samples

## Article File Connections

Article file connection resources

## Retrieve a list of article file connections

The article file connections register can return a list of records or a single record. By specifying a FileId in the URL, a single record will be returned. Not specifying a FileId will return a list of records.

##### query Parameters

| articlenumber | string  Articlenumber of file connections to list |
| --- | --- |

### Responses

### Response samples

## Create an article file connection

Create an article file connection

##### Request Body schema: \*/\*

Request body for create article file connection

| ArticleFileConnection  required | object (fortnox\_Da\_ArticleFileConnectionSinglePayloadItem) |
| --- | --- |

### Responses

### Response samples

## Remove an article file connection

Delete an article file connection

##### path Parameters

| FileId  required | string  identifies the article file connection |
| --- | --- |

### Responses

### Response samples

## Retrieve a single article file connection

Retrieve an article file connection

##### path Parameters

| FileId  required | string  identifies the article file connection |
| --- | --- |

### Responses

### Response samples

## Article Url Connections

Article url connections resources

## Retrieve a list of article url connections

The article url connections register can return a list of records or a single record. By specifying an id in the URL, a single record will be returned. Not specifying an id will return a list of records.

##### query Parameters

| articlenumber | integer \<int32>  identifies the article |
| --- | --- |

### Responses

### Response samples

## Articles

Article resources

## Retrieve a list of articles

Retrieves a list of articles. The articles are returned sorted by article number with the lowest number appearing first.

##### query Parameters

| filter | string  Enum: "active" "inactive"  possibility to filter supplier invoices |
| --- | --- |
| sortby | string  Enum: "articlenumber" "quantityinstock" "reservedquantity" "stockvalue"  field to sort returned list |
| articlenumber | string  filter by article number |
| description | string  filter by description |
| ean | string  filter by ean |
| suppliernumber | string  filter by supplier number |
| manufacturer | string  filter by manufacturer |
| manufacturerarticlenumber | string  filter by manufacturerarticlenumber |
| webshop | string  filter by web shop |
| lastmodified | string  filter by lastmodified |

### Responses

### Response samples

## Create an article

The created article will be returned if everything succeeded, if there were any problems an error will be returned.

##### Request Body schema: \*/\*

Request body for create article

| Article | object (fortnox\_ArticleSinglePayloadItem) |
| --- | --- |

### Responses

### Response samples

## Delete an article

Deletes the article permanently.

You need to supply the unique article number that was returned when the article was created or retrieved from the list of articles.

##### path Parameters

| ArticleNumber  required | integer \<int32>  identifies the article |
| --- | --- |

### Responses

### Response samples

## Retrieve an article

Retrieves the details of an article. You need to supply the unique article number that was returned when the article was created or retrieved from the list of articles.

##### path Parameters

| ArticleNumber  required | integer \<int32>  identifies the article |
| --- | --- |

### Responses

### Response samples

## Update an article

Updates the specified article with the values provided in the properties. Any property not provided will be left unchanged. You need to supply the unique article number that was returned when the article was created or retrieved from the list of articles. Note that even though the article number is writeable you can not change the number of an existing article.

##### path Parameters

| ArticleNumber  required | integer \<int32>  identifies the article |
| --- | --- |

##### Request Body schema: \*/\*

Request body for update article

| Article | object (fortnox\_ArticleSinglePayloadItem) |
| --- | --- |

### Responses

### Response samples

## fortnox\_AssetFileConnection

AssetFileConnection

## Retrieve a list of asset file connections

The asset register can return a list of assets or a single asset. By specifying a FileId in the URL, a single asset will be returned. Not specifying a FileId will return a list of records.

##### query Parameters

| assetid | string  Assetid of asset file connections to list |
| --- | --- |

### Responses

### Response samples

## Create an asset file connection

Create an asset file connection

##### Request Body schema: \*/\*

Request body for create asset file connection

| AssetId | string |
| --- | --- |
| FileId | string |
| Name | string |

### Responses

### Response samples

## Remove an asset file connection

Delete an asset file connection

##### path Parameters

| FileId  required | string  File id of asset file connection to delete |
| --- | --- |

### Responses

### Response samples

## Asset Types

Asset type resources

## Create an asset type

Update an asset

##### Request Body schema: \*/\*

Request body for update asset

| AssetType | object (fortnox\_Anl\_CreateAssetType) |
| --- | --- |

### Responses

### Response samples

## Delete an asset type

Delete an asset

##### path Parameters

| id  required | integer \<int32>  id |
| --- | --- |

### Responses

### Response samples

## Retrieve an asset type

Retrieve an asset

##### path Parameters

| id  required | integer \<int32>  id |
| --- | --- |

### Responses

### Response samples

## Update an asset type

Update an asset

##### path Parameters

| id  required | integer \<int32>  id |
| --- | --- |

##### Request Body schema: \*/\*

Request body for update asset

| AssetType | object (fortnox\_Anl\_UpdateAssetType) |
| --- | --- |

### Responses

### Response samples

## Assets

Asset resources

| **Name** | **Description** |
| --- | --- |
| active | Retrieves all active assets |
| inactive | Retrieves all inactive assets |
| fully\_depreciated | Retrieves all fully depreciated assets |
| sold | Retrieves all sold assets |
| scrapped | Retrieves all scrapped assets |
| voided | Retrieves all voided assets |

## Retrieve a list of assets

Get assets

##### query Parameters

| number | string  Asset number |
| --- | --- |
| description | string  Asset description |
| type | string  Asset type |
| lastmodified | string \<date>  Filter on last modified date |

### Responses

### Response samples

## Create an Asset

The created asset will be returned if everything succeeded, if there were any problems an error will be returned.

##### Request Body schema: \*/\*

Request body for create asset

| Asset | object (fortnox\_Anl\_AssetsSinglePayloadItem) |
| --- | --- |

### Responses

### Response samples

## Change manual OB value of an Asset

The updated asset will be returned if everything succeeded, if there were any problems an error will be returned.

##### path Parameters

| Id  required | string  Asset ID |
| --- | --- |

##### Request Body schema: \*/\*

Request body for update asset

| Amount | integer \<int32> |
| --- | --- |
| AssetIds | Array of integers \<int32> \[ items \<int32 > \] |