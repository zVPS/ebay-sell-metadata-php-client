# # ReturnPolicy

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**category_id** | **string** | The category ID to which the return policies apply. | [optional]
**category_tree_id** | **string** | A value that indicates the root node of the category tree used for the response set. Each marketplace is based on a category tree whose root node is indicated by this unique category ID value. All category policy information returned by this call pertains to the categories included below this root node of the tree. A category tree is a hierarchical framework of eBay categories that begins at the root node of the tree and extends to include all the child nodes in the tree. Each child node in the tree is an eBay category that is represented by a unique categoryId value. Within a category tree, the root node has no parent node and leaf nodes are nodes that have no child nodes. | [optional]
**domestic** | [**\Ebay\Sell\Metadata\Model\ReturnPolicyDetails**](ReturnPolicyDetails.md) |  | [optional]
**international** | [**\Ebay\Sell\Metadata\Model\ReturnPolicyDetails**](ReturnPolicyDetails.md) |  | [optional]
**required** | **bool** | If set to true, this flag indicates that you must specify a return policy for items listed in the associated category. Note that not accepting returns (setting returnsAcceptedEnabled to false) is a valid return policy. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
