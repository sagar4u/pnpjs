# @pnp/sp/features

Features module provides method to get the details of activated features. And to activate/deactive features scoped at Site Collection and Web.

## IFeatures

[![](https://img.shields.io/badge/Invokable-informational.svg)](../invokable.md) [![](https://img.shields.io/badge/Selective%20Imports-informational.svg)](../selective-imports.md)

Represents a collection of features. SharePoint Site and Web will have collection of features

|Scenario|Import Statement|
|--|--|
|Selective 1|import { sp } from "@pnp/sp";<br />import "@pnp/sp/src/features/site";|
|Selective 2|import { sp } from "@pnp/sp";<br />import "@pnp/sp/src/webs";<br/>import "@pnp/sp/src/features/web";|
|Selective 3|import { sp } from "@pnp/sp";<br />import "@pnp/sp/src/features";|
|Selective 4|import { sp } from "@pnp/sp";<br />import "@pnp/sp/src/webs";<br/>import "@pnp/sp/src/features";|
|Preset: All|import { sp, IFeatures, Features } from "@pnp/sp/presets/all";|

### getById

Gets the information about a feature for the given GUID

```TypeScript
import { sp } from "@pnp/sp";
import "@pnp/sp/src/webs";
import "@pnp/sp/src/features";

const webFeatureId = "guid-of-web-feature";
const webFeature = await sp.web.features.getById(webFeatureId)();

const siteFeatureId = "guid-of-site-scope-feature";
const siteFeature = await sp.site.features.getById(siteFeatureId)();
```

### add

Adds (activates) a feature at the Site or Web level

```TypeScript
import { sp } from "@pnp/sp";
import "@pnp/sp/src/webs";
import "@pnp/sp/src/features";

const webFeatureId = "guid-of-web-feature";
let res = await sp.web.features.add(webFeatureId);
// Activate with force
res = await sp.web.features.add(webFeatureId, true);
```

### remove

Removes (deactivates) the specified feature from the SharePoint Site or Web
```TypeScript
import { sp } from "@pnp/sp";
import "@pnp/sp/src/webs";
import "@pnp/sp/src/features";

const webFeatureId = "guid-of-web-feature";
let res = await sp.web.features.remove(webFeatureId);
// Deactivate with force
res = await sp.web.features.remove(webFeatureId, true);
```

## IFeature  

Represents an instance of a SharePoint feature.

[![](https://img.shields.io/badge/Invokable-informational.svg)](../invokable.md) [![](https://img.shields.io/badge/Selective%20Imports-informational.svg)](../selective-imports.md)  

|Scenario|Import Statement|
|--|--|
|Selective 1|import { sp } from "@pnp/sp";<br />import "@pnp/sp/src/features/site";|
|Selective 2|import { sp } from "@pnp/sp";<br />import "@pnp/sp/src/webs";<br/>import "@pnp/sp/src/features/web";|
|Selective 3|import { sp } from "@pnp/sp";<br />import "@pnp/sp/src/features";|
|Selective 4|import { sp } from "@pnp/sp";<br />import "@pnp/sp/src/webs";<br/>import "@pnp/sp/src/features";|
|Preset: All|import { sp, IFeatures, Features, IFeature, Feature } from "@pnp/sp/presets/all";|

### deactivate

```TypeScript
import { sp } from "@pnp/sp";
import "@pnp/sp/src/webs";
import "@pnp/sp/src/features";

const webFeatureId = "guid-of-web-feature";
sp.web.features.getById(webFeatureId).deactivate()

// Deactivate with force
sp.web.features.getById(webFeatureId).deactivate(true)
```