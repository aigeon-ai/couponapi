# Couponapi

## Introduction

Welcome to the CouponAPI! This API provides access to a variety of coupon offers, allowing users to retrieve, filter, and obtain detailed information about current promotions. With our API, you can easily access incremental feeds of coupon offers, get details for specific offers, and filter offers by store or category. This documentation outlines the available endpoints and their functionalities.

## Tools Overview

### 1. Get Incremental Feed

- **Name**: `get_incremental_feed`
- **Description**: Retrieve an incremental feed of coupon offers from CouponAPI.org. This endpoint returns new, updated, and suspended offers since the last extract time. If no `last_extract` is provided, it returns all currently active offers. Set `off_record=True` to avoid updating the last extract time in the system.

#### Input Schema

- `last_extract`: Last extract timestamp as UNIX timestamp in seconds (epoch). If not provided, returns all active offers.
- `response_format`: Response format: 'json' or 'csv'. Defaults to 'json'.
- `limit`: Maximum number of offers to return. Optional parameter.
- `store_id`: Filter by specific store ID. Optional parameter.
- `category`: Filter by category. Optional parameter.
- `off_record`: When True, does not update the last extract time, allowing repeated retrieval of incremental data. Defaults to False.

### 2. Get Offer Details

- **Name**: `get_offer_details`
- **Description**: Retrieve detailed information for a specific offer. This tool filters the incremental feed to return details for a specific offer ID.

#### Input Schema

- `offer_id`: The unique offer ID to get details for. (Required)

### 3. Get Offers by Store

- **Name**: `get_offers_by_store`
- **Description**: Retrieve all offers for a specific store. This endpoint returns all current offers for the specified store name.

#### Input Schema

- `store_name`: Store name to filter offers by. (Required)

### 4. Get Offers by Category

- **Name**: `get_offers_by_category`
- **Description**: Retrieve all offers for a specific category. This endpoint returns all current offers for the specified category.

#### Input Schema

- `category`: Category to filter offers by. (Required)

## Conclusion

The CouponAPI provides a flexible and efficient way to access coupon offers. Whether you're looking for incremental updates, specific offer details, or offers filtered by store or category, our API has you covered. For more information on how to use these endpoints, please refer to the individual tool descriptions above.
