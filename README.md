# Sunglass Hut Unofficial API

This unofficial API provides endpoints for retrieving product information, related products, and searching for products by category or brand. It allows developers to integrate Sunglass Hut product data into their applications.
This API is listed on rapidadpi -> https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/sunglass-hut

## GET /product/info

This endpoint retrieves product information based on the provided URL.

### Query Parameters

- `url` (required): The URL of the product whose information is to be fetched.

### Responses

#### Success (200)
Returns the product information in JSON format.

- **Response Body:**
  ```json
  {
    "name": "Product Name",
    "description": "Product Description",
    "image": "Image URL",
    "url": "Product URL",
    "itemCondition": "Item Condition",
    "brand": "Brand Name",
    "color": "Color",
    "gtin": "GTIN",
    "gtin13": "GTIN-13",
    "mpn": "MPN",
    "audience": "Audience",
    "material": "Material",
    "category": "Category",
    "sku": "SKU",
    "offers": "Offers"
  }



## GET /product/:objectId/related_products

This endpoint retrieves related products for a given product based on its object ID.

### Path Parameters

- `objectId` (required): The object ID of the product whose related products are to be fetched.

### Query Parameters

- `pageNumber` (optional): The page number for pagination of the related products. Defaults to 1.

### Responses

#### Success (200)
Returns a list of related products in JSON format.

- **Response Body:**
  ```json
  [
    {
      "objectID": "Related Object ID",
      "productId": "Product ID",
      "inventoryQuantity": "Inventory Quantity",
      "languageLocale": "Language Locale",
      "longDescription": "Long Description",
      "media": "Media Information",
      "modifiedTime": "Modified Time",
      "parentProductId": "Parent Product ID",
      "prices": "Prices",
      "url": "Product URL",
      "storeId": "Store ID"
    },
    ...
  ]

## GET /product/category/:category

This endpoint retrieves products by the specified category.

### Path Parameters

- `category` (required): The category of products to be fetched. Allowed categories are:
  - `gender_male`
  - `gender_female`
  - `brands_rayban`
  - `designer_sunglasses`

### Query Parameters

- `pageNumber` (optional): The page number for pagination. Defaults to 0 if not provided.
- `perPage` (optional): The number of products per page. Defaults to 7 if not provided.

### Responses

#### Success (200)
Returns the products in the specified category in JSON format.

- **Response Body:**
  ```json
  [
    {
      "objectID": "Object ID",
      "productId": "Product ID",
      "inventoryQuantity": "Inventory Quantity",
      "languageLocale": "Language Locale",
      "longDescription": "Long Description",
      "media": "Media",
      "modifiedTime": "Modified Time",
      "parentProductId": "Parent Product ID",
      "prices": "Prices",
      "url": "Product URL",
      "storeId": "Store ID"
    }
  ]

# Endpoint Description

## GET /product/search

This endpoint searches for products based on the provided query.

### Query Parameters

- `q` (required): The search query.
- `pageNumber` (optional): The page number for pagination. Defaults to 0 if not provided.
- `perPage` (optional): The number of products per page. Defaults to 7 if not provided.

### Responses

#### Success (200)
Returns the search results in JSON format.

- **Response Body:**
  ```json
  [
    {
      "objectID": "Object ID",
      "productId": "Product ID",
      "inventoryQuantity": "Inventory Quantity",
      "languageLocale": "Language Locale",
      "longDescription": "Long Description",
      "media": "Media",
      "modifiedTime": "Modified Time",
      "parentProductId": "Parent Product ID",
      "prices": "Prices",
      "url": "Product URL",
      "storeId": "Store ID"
    }
  ]


## POST /product/brand

This endpoint retrieves products and their attributes based on the provided brand names.

### Request Body

- `brands` (required): An array of brand names.

### Query Parameters

- `q` (optional): The search query.
- `pageNumber` (optional): The page number for pagination. Defaults to 0 if not provided.
- `perPage` (optional): The number of products per page. Defaults to 7 if not provided.

### Responses

#### Success (200)
Returns the products and their attributes in JSON format.

- **Response Body:**
  ```json
  [
    {
      "objectID": "Object ID",
      "productId": "Product ID",
      "inventoryQuantity": "Inventory Quantity",
      "languageLocale": "Language Locale",
      "longDescription": "Long Description",
      "media": "Media",
      "modifiedTime": "Modified Time",
      "parentProductId": "Parent Product ID",
      "prices": "Prices",
      "url": "Product URL",
      "storeId": "Store ID"
    }
  ]
