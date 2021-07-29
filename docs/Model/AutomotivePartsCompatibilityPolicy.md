# # AutomotivePartsCompatibilityPolicy

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**category_id** | **string** | The category ID to which the automotive-parts-compatibility policies apply. | [optional]
**category_tree_id** | **string** | A value that indicates the root node of the category tree used for the response set. Each marketplace is based on a category tree whose root node is indicated by this unique category ID value. All category policy information returned by this call pertains to the categories included below this root node of the tree. A category tree is a hierarchical framework of eBay categories that begins at the root node of the tree and extends to include all the child nodes in the tree. Each child node in the tree is an eBay category that is represented by a unique categoryId value. Within a category tree, the root node has no parent node and leaf nodes are nodes that have no child nodes. | [optional]
**compatibility_based_on** | **string** | Indicates whether the category supports parts compatibility by either ASSEMBLY or by SPECIFICATION. For implementation help, refer to &lt;a href&#x3D;&#39;https://developer.ebay.com/api-docs/sell/metadata/types/sel:CompatibilityTypeEnum&#39;&gt;eBay API documentation&lt;/a&gt; | [optional]
**compatible_vehicle_types** | **string[]** | Indicates the compatibility classification of the part based on high-level vehicle types. | [optional]
**max_number_of_compatible_vehicles** | **int** | Specifies the maximum number of compatible vehicle-applications allowed per item. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
