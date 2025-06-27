# Announcement Model #

This directory contains the minimal artefacts that are intended for creating the first version of the form generation implementation.

## Changelog ##
26.06.2025

Business Case: Currently, it is not intended to offer several business cases per announcement type. Instead, there is a separate announcement type for each specialization of an announcement. This simplifies the configuration file.

**Name:** A new multilingual element “name” has been added.

**Themes, Languages, OrganisationType, PublicationDay, Holidays:** Values are provided as keys in an array

**Gazette:** This element is no longer necessary for the following reasons: 
- Provider (not editor) is responsible for the announcement type.
- The announcement type therefore does not reference an editor (no element: "gazette").
- The announcement type can be used and configured by an editor:
  - Individual elements of the announcement type can be overridden (elements to be defined).
  - Editor-specific elements must be defined. E.g. price for primary publication.
- Example: There is a "Construction publication" announcement type. Editors can use and configure this. There is not a separate announcement type for a construcion publication per editor.

**Configuration of value types:** A mechanism is needed to configure certain aspects (restrictions and validations) of the value types when used in a specific announcement type.
The value type of a term element is defined in the catalog file as before. However, the configuration of the value type is made in the config file using the element "valueTypeConfig". The parameters for the configuration must be processed in the statically coded value type. Some possible parameterizations were used as examples in the sample configurations.

**Enumerations:** The values of the enumerations are also added as a configuration in the announcement type (s. example BP).
