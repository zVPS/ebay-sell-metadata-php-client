# Ebay\Sell\Metadata\MarketplaceApi

All URIs are relative to https://api.ebay.com/sell/metadata/v1.

Method | HTTP request | Description
------------- | ------------- | -------------
[**getAutomotivePartsCompatibilityPolicies()**](MarketplaceApi.md#getAutomotivePartsCompatibilityPolicies) | **GET** /marketplace/{marketplace_id}/get_automotive_parts_compatibility_policies | 
[**getItemConditionPolicies()**](MarketplaceApi.md#getItemConditionPolicies) | **GET** /marketplace/{marketplace_id}/get_item_condition_policies | 
[**getListingStructurePolicies()**](MarketplaceApi.md#getListingStructurePolicies) | **GET** /marketplace/{marketplace_id}/get_listing_structure_policies | 
[**getNegotiatedPricePolicies()**](MarketplaceApi.md#getNegotiatedPricePolicies) | **GET** /marketplace/{marketplace_id}/get_negotiated_price_policies | 
[**getProductAdoptionPolicies()**](MarketplaceApi.md#getProductAdoptionPolicies) | **GET** /marketplace/{marketplace_id}/get_product_adoption_policies | 
[**getReturnPolicies()**](MarketplaceApi.md#getReturnPolicies) | **GET** /marketplace/{marketplace_id}/get_return_policies | 


## `getAutomotivePartsCompatibilityPolicies()`

```php
getAutomotivePartsCompatibilityPolicies($marketplace_id, $filter): \Ebay\Sell\Metadata\Model\AutomotivePartsCompatibilityPolicyResponse
```



This method returns the eBay policies that define how to list automotive-parts-compatibility items in the categories of a specific marketplace. By default, this method returns the entire category tree for the specified marketplace. You can limit the size of the result set by using the filter query parameter to specify only the category IDs you want to review. Tip: This method can return a very large response payload and we strongly recommend you get the results from this call in a GZIP file by including the following HTTP header with your request: &nbsp;&nbsp;Accept-Encoding: application/gzip

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Client Credentials
$config = Ebay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Metadata\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | This path parameter specifies the eBay marketplace for which policy information is retrieved. Note: Only the following eBay marketplaces support automotive parts compatibility: EBAY_US EBAY_AU EBAY_CA EBAY_DE EBAY_ES EBAY_FR EBAY_GB EBAY_IT
$filter = 'filter_example'; // string | This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character ('|'). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter=categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &nbsp;&nbsp;filter=categoryIds%3A%7B100%7C101%7C102%7D

try {
    $result = $apiInstance->getAutomotivePartsCompatibilityPolicies($marketplace_id, $filter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->getAutomotivePartsCompatibilityPolicies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| This path parameter specifies the eBay marketplace for which policy information is retrieved. Note: Only the following eBay marketplaces support automotive parts compatibility: EBAY_US EBAY_AU EBAY_CA EBAY_DE EBAY_ES EBAY_FR EBAY_GB EBAY_IT |
 **filter** | **string**| This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character (&#39;|&#39;). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter&#x3D;categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &amp;nbsp;&amp;nbsp;filter&#x3D;categoryIds%3A%7B100%7C101%7C102%7D | [optional]

### Return type

[**\Ebay\Sell\Metadata\Model\AutomotivePartsCompatibilityPolicyResponse**](../Model/AutomotivePartsCompatibilityPolicyResponse.md)

### Authorization

[Client Credentials](../../README.md#Client Credentials)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getItemConditionPolicies()`

```php
getItemConditionPolicies($marketplace_id, $filter): \Ebay\Sell\Metadata\Model\ItemConditionPolicyResponse
```



This method returns item condition metadata on one, multiple, or all eBay categories on an eBay marketplace. This metadata consists of the different item conditions (with IDs) that an eBay category supports, and a boolean to indicate if an eBay category requires an item condition. The identifier of the eBay marketplace is passed in as a path parameter, and unless one or more eBay category IDs are passed in through the filter query parameter, this method will return metadata on every single category for the specified marketplace. If you only want to view item condition metadata for one eBay category or a select group of eBay categories, you can pass in up to 50 eBay category ID through the filter query parameter. Important!: Certified Refurbished-eligible sellers must use an OAuth token created with the authorization code grant flow and https://api.ebay.com/oauth/api_scope/sell.inventory scope in order to retrieve the 'Certified Refurbished' condition (condition ID 2000) for the relevant categories. The Certified Refurbished item condition will not be returned if an OAuth token created with the client credentials grant flow and https://api.ebay.com/oauth/api_scope scope is used, or if any seller is not eligible to list with that item condition. See the Specifying OAuth scopes topic for more information about specifying scopes. Tip: If you retrieve metadata on all eBay categories for a marketplace, the response payload can be quite large. For this reason, we suggest that you consider using the Accept-Encoding request header and set its value to application/gzip. By doing this, the response payload output will be compressed into a GZIP file.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Authorization Code
$config = Ebay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: Client Credentials
$config = Ebay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Metadata\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components.
$filter = 'filter_example'; // string | This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character ('|'). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter=categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &nbsp;&nbsp;filter=categoryIds%3A%7B100%7C101%7C102%7D

try {
    $result = $apiInstance->getItemConditionPolicies($marketplace_id, $filter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->getItemConditionPolicies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components. |
 **filter** | **string**| This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character (&#39;|&#39;). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter&#x3D;categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &amp;nbsp;&amp;nbsp;filter&#x3D;categoryIds%3A%7B100%7C101%7C102%7D | [optional]

### Return type

[**\Ebay\Sell\Metadata\Model\ItemConditionPolicyResponse**](../Model/ItemConditionPolicyResponse.md)

### Authorization

[Authorization Code](../../README.md#Authorization Code), [Client Credentials](../../README.md#Client Credentials)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getListingStructurePolicies()`

```php
getListingStructurePolicies($marketplace_id, $filter): \Ebay\Sell\Metadata\Model\ListingStructurePolicyResponse
```



This method returns the eBay policies that define the allowed listing structures for the categories of a specific marketplace. The listing-structure policies currently pertain to whether or not you can list items with variations. By default, this method returns the entire category tree for the specified marketplace. You can limit the size of the result set by using the filter query parameter to specify only the category IDs you want to review. Tip: This method can return a very large response payload and we strongly recommend you get the results from this call in a GZIP file by including the following HTTP header with your request: &nbsp;&nbsp;Accept-Encoding: application/gzip

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Client Credentials
$config = Ebay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Metadata\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components.
$filter = 'filter_example'; // string | This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character ('|'). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter=categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &nbsp;&nbsp;filter=categoryIds%3A%7B100%7C101%7C102%7D

try {
    $result = $apiInstance->getListingStructurePolicies($marketplace_id, $filter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->getListingStructurePolicies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components. |
 **filter** | **string**| This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character (&#39;|&#39;). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter&#x3D;categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &amp;nbsp;&amp;nbsp;filter&#x3D;categoryIds%3A%7B100%7C101%7C102%7D | [optional]

### Return type

[**\Ebay\Sell\Metadata\Model\ListingStructurePolicyResponse**](../Model/ListingStructurePolicyResponse.md)

### Authorization

[Client Credentials](../../README.md#Client Credentials)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getNegotiatedPricePolicies()`

```php
getNegotiatedPricePolicies($marketplace_id, $filter): \Ebay\Sell\Metadata\Model\NegotiatedPricePolicyResponse
```



This method returns the eBay policies that define the supported negotiated price features (like &quot;best offer&quot;) for the categories of a specific marketplace. By default, this method returns the entire category tree for the specified marketplace. You can limit the size of the result set by using the filter query parameter to specify only the category IDs you want to review. Tip: This method can return a very large response payload and we strongly recommend you get the results from this call in a GZIP file by including the following HTTP header with your request: &nbsp;&nbsp;Accept-Encoding: application/gzip

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Client Credentials
$config = Ebay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Metadata\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components.
$filter = 'filter_example'; // string | This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character ('|'). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter=categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &nbsp;&nbsp;filter=categoryIds%3A%7B100%7C101%7C102%7D

try {
    $result = $apiInstance->getNegotiatedPricePolicies($marketplace_id, $filter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->getNegotiatedPricePolicies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components. |
 **filter** | **string**| This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character (&#39;|&#39;). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter&#x3D;categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &amp;nbsp;&amp;nbsp;filter&#x3D;categoryIds%3A%7B100%7C101%7C102%7D | [optional]

### Return type

[**\Ebay\Sell\Metadata\Model\NegotiatedPricePolicyResponse**](../Model/NegotiatedPricePolicyResponse.md)

### Authorization

[Client Credentials](../../README.md#Client Credentials)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getProductAdoptionPolicies()`

```php
getProductAdoptionPolicies($marketplace_id, $filter): \Ebay\Sell\Metadata\Model\ProductAdoptionPolicyResponse
```



This method retrieves a list of leaf categories for a marketplace and identifies the categories that require items to have an eBay product ID value in order to be listed in those categories. An eBay product ID value (known as an &quot;ePID&quot;) is a value that references a specific product in the eBay Catalog. Important: eBay catalog product adoption is not currently required for any product categories. If product adoption requirements change, they will be noted here. Use the marketplace_id path parameter to specify the marketplace you want to review and use the filter query parameter to limit the categories returned in the response. Tip: This method can return a very large response payload and we strongly recommend you get the results from this call in a GZIP file by including the following HTTP header with your request: &nbsp;&nbsp;Accept-Encoding: application/gzip

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Client Credentials
$config = Ebay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Metadata\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components.
$filter = 'filter_example'; // string | This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character ('|'). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter=categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &nbsp;&nbsp;filter=categoryIds%3A%7B100%7C101%7C102%7D

try {
    $result = $apiInstance->getProductAdoptionPolicies($marketplace_id, $filter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->getProductAdoptionPolicies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components. |
 **filter** | **string**| This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character (&#39;|&#39;). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter&#x3D;categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &amp;nbsp;&amp;nbsp;filter&#x3D;categoryIds%3A%7B100%7C101%7C102%7D | [optional]

### Return type

[**\Ebay\Sell\Metadata\Model\ProductAdoptionPolicyResponse**](../Model/ProductAdoptionPolicyResponse.md)

### Authorization

[Client Credentials](../../README.md#Client Credentials)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getReturnPolicies()`

```php
getReturnPolicies($marketplace_id, $filter): \Ebay\Sell\Metadata\Model\ReturnPolicyResponse
```



This method returns the eBay policies that define whether or not you must include a return policy for the items you list in the categories of a specific marketplace, plus the guidelines for creating domestic and international return policies in the different eBay categories. By default, this method returns the entire category tree for the specified marketplace. You can limit the size of the result set by using the filter query parameter to specify only the category IDs you want to review. Tip: This method can return a very large response payload and we strongly recommend you get the results from this call in a GZIP file by including the following HTTP header with your request: &nbsp;&nbsp;Accept-Encoding: application/gzip

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Client Credentials
$config = Ebay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Metadata\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components.
$filter = 'filter_example'; // string | This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character ('|'). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter=categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &nbsp;&nbsp;filter=categoryIds%3A%7B100%7C101%7C102%7D

try {
    $result = $apiInstance->getReturnPolicies($marketplace_id, $filter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->getReturnPolicies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components. |
 **filter** | **string**| This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character (&#39;|&#39;). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter&#x3D;categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &amp;nbsp;&amp;nbsp;filter&#x3D;categoryIds%3A%7B100%7C101%7C102%7D | [optional]

### Return type

[**\Ebay\Sell\Metadata\Model\ReturnPolicyResponse**](../Model/ReturnPolicyResponse.md)

### Authorization

[Client Credentials](../../README.md#Client Credentials)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
