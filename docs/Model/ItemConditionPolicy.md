# # ItemConditionPolicy

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**category_id** | **string** | The category ID to which the item-condition policy applies. | [optional]
**category_tree_id** | **string** | A value that indicates the root node of the category tree used for the response set. Each marketplace is based on a category tree whose root node is indicated by this unique category ID value. All category policy information returned by this call pertains to the categories included below this root node of the tree. A category tree is a hierarchical framework of eBay categories that begins at the root node of the tree and extends to include all the child nodes in the tree. Each child node in the tree is an eBay category that is represented by a unique categoryId value. Within a category tree, the root node has no parent node and leaf nodes are nodes that have no child nodes. | [optional]
**item_condition_required** | **bool** | This flag denotes whether or not you must list the item condition in a listing for the specified category. If set to true, you must specify an item condition for the associated category. | [optional]
**item_conditions** | [**\Ebay\Sell\Metadata\Model\ItemCondition[]**](ItemCondition.md) | The item-condition values allowed in the category. Note: In all eBay marketplaces, Condition ID 2000 now maps to an item condition of &#39;Certified Refurbished&#39;, and not &#39;Manufacturer Refurbished&#39;. To list an item as &#39;Certified Refurbished&#39;, a seller must be pre-qualified by eBay for this feature. Any seller who is not eligible for this feature will be blocked if they try to create a new listing or revise an existing listing with this item condition. Any active listings on any eBay marketplace that had &#39;Manufacturer Refurbished&#39; as the item condition should have been automatically updated by eBay to the &#39;Seller Refurbished&#39; item condition (Condition ID 2500). Any seller that is interested in eligibility requirements to list with &#39;Certified Refurbished&#39; should see the Certified refurbished program page in Seller Center. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
