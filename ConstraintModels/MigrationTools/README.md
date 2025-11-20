# Migration Tools for Digital Insurance Constraint Engine

This directory contains utilities designed to streamline the deployment and migration of Constraint Rule Engine assets across Salesforce orgs. These tools enable you to efficiently move CML rule sets and associated product model metadata between your instances.

---

## Overview

When implementing the Constraint Rule Engine in Digital Insurance, you'll often need to:
- **Migrate CML rule sets** from one org to another
- **Transfer complete product hierarchies** with all dependencies intact
- Transform **standard/legacy configuration rules** to **constraints**

The tools in this directory address these needs with production-ready utilities that handle the complexity of cross-org data migration while preserving metadata relationships and dependencies.

---

## Available Tools

### 1. [CML Migration Tool](https://github.com/gkibilov/cml-migration/tree/main)

The **CML Migration Tool** enables seamless import, export, and deployment of Constraint Modeling Language (CML) rule sets across Salesforce orgs. This tool is essential for:
- Moving rule sets from sandbox to production environments
- Updating of the existing rule sets 
- Creating backups of your CML configurations
- Sharing rule set templates across multiple orgs


**Note**: This tool assumes target org already has relevant Context Definition and PCM data like Attributes, Product Classifications, Products and Product Related Components.

#### How to Use the CML Migration Tool

1. Install [Salesforce CLI](https://developer.salesforce.com/tools/salesforcecli)
2. Authorize source org and target org
    ```
    sf auth:web:login --instance-url https://<source-instance>.salesforce.com -a srcOrg
    sf auth:web:login --instance-url https://<target-instance>.salesforce.com -a tgtOrg
    ```
3. Check connection using ```sf org list```
4. Export from Source Org using ```python export_cml.py --developerName [Constraint Model API Name]```
5. Import to Target Org using ```python import_cml.py```

🔧 Requirements
- Python 3.9+
- Salesforce CLI (sf)
- Connected orgs with accessible metadata API
---

### 2. [Multi Cloud Data Migrator for Product Models](https://github.com/sf-mcdm/multi-cloud-data-migrator)

The **Multi Cloud Data Migrator** is a comprehensive tool for migrating Insurance product hierarchy metadata and data across orgs. It ensures that all components of your product model remain consistent during transfer.

**What Gets Migrated:**
- Product Definitions and hierarchies(Product Related Components)
- Attribute Categories and Definitions
- Picklist and Picklist Values 
- Pricebook Entries
- and more...

**Key Features:**
- Dependency-aware sequencing prevents broken references
- Automated or semi-automated migration workflows
- Support for complex product hierarchies
- Validation to ensure data integrity post-migration

#### How to Use the Multi Cloud Data Migrator User Interface

1. Install [Salesforce CLI](https://developer.salesforce.com/tools/salesforcecli)
2. Install Multi Cloud Data Migrator Plugin using ```sf plugins install sf-mcdm/multi-cloud-data-migrator```
3. Authorize source org and target org
    ```
    sf auth:web:login --instance-url https://<source-instance>.salesforce.com -a srcOrg
    sf auth:web:login --instance-url https://<target-instance>.salesforce.com -a tgtOrg
    ```
4. Check connection using ```sf org list```
5. Open the Web App user interface using ```sf multi-cloud-data-migrator:ui```
6. Choose **Deep Clone Migration Plan** and **Revenue-Cloud-Advanced-Product**
7. Input your source and target org, and root product's SKU(Stock Keeping Unit), you can put multiple ones separating by comma
8. Click **View Plan** and make sure all Key fields in SObject is populated (**note**: this is very important for clean product structure migration) 
9. Click "Start Migration", you can monitor the progress in "Job Monitor" tab and issues in "Failure and Skip Files" tab 

#### SObject Keys Reference

For Step 8: critical to ensure your data is clean and properly prepared
- Check Your Keys: Use the View Plan button to review the migration strategy.
- Ensure Uniqueness: Verify that all Key fields and composite key combinations are populated and unique in the source data.
- Validate Data: Duplicate or missing keys will cause records to be skipped or linked incorrectly. The migration will not run as expected if the underlying data quality is poor.

| SObject | Key |
|---------|-----|
| UnitOfMeasureClass | Code |
| UnitOfMeasure | Name |
| UnitOfMeasureClass | Code |
| AttributeCategory | Code |
| AttributePicklist | Name |
| AttributePicklistValue | Code |
| AttributeDefinition | Code |
| AttributeCategoryAttribute | AttributeCategory.Code, AttributeDefinition.Code |
| ProductClassification | Code |
| ProductClassificationAttr | AttributeDefinition.Code, ProductClassification.Code |
| ProductSpecificationType | DeveloperName |
| ProductSpecificationRecType | DeveloperName |
| Product2 | StockKeepingUnit |
| ProductAttributeDefinition | AttributeDefinitionId, Product2Id, ProductClassificationAttributeId |
| Product2DataTranslation | Parent.StockKeepingUnit, Language |
| CostBook | Name |
| CostBookEntry | CostBook.Name, Product.StockKeepingUnit |
| Pricebook2 | Name |
| ProrationPolicy | Name |
| ProductSellingModel | Name |
| ProductSellingModelOption | ProductSellingModel.Name, Product2.StockKeepingUnit |
| PricebookEntry | ProductSellingModel.Name, Product2.StockKeepingUnit, Pricebook2.Name |
| ProductCatalog | Code |
| ProductCategory | Code |
| ProductCategoryDataTranslation | Parent.Code, Language |
| ProductCategoryProduct | ProductCategory.Code, Product.StockKeepingUnit |
| ProductComponentGroup | Code |
| ProductComponentGrpOverride | OverrideContext.Name, ProductComponentGroup.Code |
| ProductRelatedComponent | ParentProduct.StockKeepingUnit, ProductComponentGroup.Code, ProductRelationshipType.Name |
| ProductRelComponentOverride | OverrideContext.Name, ProductRelatedComponentId |
| PriceAdjustmentSchedule | Name |
| PriceAdjustmentTier | PriceAdjustmentSchedule.Name, Product2.StockKeepingUnit |
| BundleBasedAdjustment | PriceAdjustmentSchedule.Name, ParentProduct.StockKeepingUnit, Product.StockKeepingUnit |
| AttributeBasedAdjRule | Name |
| AttributeAdjustmentCondition | AttributeBasedAdjRule.Name, AttributeDefinition.Name, Product.StockKeepingUnit |
| AttributeBasedAdjustment | AttributeBasedAdjRule.Name, PriceAdjustmentSchedule.Name, Product.StockKeepingUnit |
| ProductConfigurationFlow | FlowIdentifier |
| ProductConfigFlowAssignment | ProductConfigurationFlow.FlowIdentifier |


---

## Prerequisites

Before using these migration tools, ensure you have:
- Digital Insurance product licenses configured in target orgs
- Constraint Rule Engine enabled in target orgs (for CML migrations)
- Appropriate API access and authentication credentials

---

## Support and Troubleshooting

If you encounter issues during migration:
- Check Failure/Skip log
- Verify that all prerequisites are met in the target org
- Ensure product model metadata exists before migrating dependent CML rules

For additional support, refer to the main repository documentation or contact Salesforce support.

---

## Additional Resources

- [Main Repository README](../README.md)
- [Example CML Rule Sets](../ExampleCMLRuleSets/README.md)
- [Product Models Documentation](../ProductModels/README.md)

