# Ebay\Sell\CountryApi

All URIs are relative to https://api.ebay.com/sell/metadata/v1.

Method | HTTP request | Description
------------- | ------------- | -------------
[**getSalesTaxJurisdictions()**](CountryApi.md#getSalesTaxJurisdictions) | **GET** /country/{countryCode}/sales_tax_jurisdiction | 


## `getSalesTaxJurisdictions()`

```php
getSalesTaxJurisdictions($country_code): \Ebay\Sell\Metadata\Model\SalesTaxJurisdictions
```



This method retrieves all the sales tax jurisdictions for the country that you specify in the countryCode path parameter. Countries with valid sales tax jurisdictions are Canada and the US. The response from this call tells you the jurisdictions for which a seller can configure tax tables. Although setting up tax tables is optional, you can use the createOrReplaceSalesTax in the Account API call to configure the tax tables for the jurisdictions you sell to.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: Client Credentials
$config = Ebay\Sell\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Ebay\Sell\Api\CountryApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$country_code = 'country_code_example'; // string | This path parameter specifies the two-letter ISO 3166 country code for the country whose jurisdictions you want to retrieve. eBay provides sales tax jurisdiction information for Canada and the United States.Valid values for this path parameter are CA and US.

try {
    $result = $apiInstance->getSalesTaxJurisdictions($country_code);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CountryApi->getSalesTaxJurisdictions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **country_code** | **string**| This path parameter specifies the two-letter ISO 3166 country code for the country whose jurisdictions you want to retrieve. eBay provides sales tax jurisdiction information for Canada and the United States.Valid values for this path parameter are CA and US. |

### Return type

[**\Ebay\Sell\Metadata\Model\SalesTaxJurisdictions**](../Model/SalesTaxJurisdictions.md)

### Authorization

[Client Credentials](../../README.md#Client Credentials)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
