---
title: "Module mssql"
title_tag: "Module mssql | Package @pulumi/azure | Node.js SDK"
linktitle: "mssql"
meta_desc: "Explore members of the mssql module in the @pulumi/azure package."
---

<!-- WARNING: this page was generated by a tool. Do not edit it by hand. -->
<!-- To change it, please see https://github.com/pulumi/docs/tree/master/tools/tscdocgen. -->


> This provider is a derived work of the [Terraform Provider](https://github.com/terraform-providers/terraform-provider-azurerm)
> distributed under [MPL 2.0](https://www.mozilla.org/en-US/MPL/2.0/). If you encounter a bug or missing feature,
> first check the [`pulumi/pulumi-azure` repo](https://github.com/pulumi/pulumi-azure/issues); however, if that doesn't turn up anything,
> please consult the source [`terraform-providers/terraform-provider-azurerm` repo](https://github.com/terraform-providers/terraform-provider-azurerm/issues).





<h3>Resources</h3>
<ul class="api">
    <li><a href="#ElasticPool"><span class="symbol resource"></span>ElasticPool</a></li>
</ul>

<h3>Data Sources</h3>
<ul class="api">
    <li><a href="#getElasticPool"><span class="symbol datasource"></span>getElasticPool</a></li>
</ul>

<h3>Others</h3>
<ul class="api">
    <li><a href="#ElasticPoolArgs"><span class="symbol api"></span>ElasticPoolArgs</a></li>
    <li><a href="#ElasticPoolState"><span class="symbol api"></span>ElasticPoolState</a></li>
    <li><a href="#GetElasticPoolArgs"><span class="symbol api"></span>GetElasticPoolArgs</a></li>
    <li><a href="#GetElasticPoolResult"><span class="symbol api"></span>GetElasticPoolResult</a></li>
</ul>


<h2 id="resources">Resources</h2>
<h3 class="pdoc-module-header" id="ElasticPool" data-link-title="ElasticPool">
    <a href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L48">
        Resource <strong>ElasticPool</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kr'>class</span> <span class='nx'>ElasticPool</span> <span class='kr'>extends</span> <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResource'>CustomResource</a></code></pre>

Allows you to manage an Azure SQL Elastic Pool via the `2017-10-01-preview` API which allows for `vCore` and `DTU` based configurations.

#### Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure from "@pulumi/azure";

const exampleResourceGroup = new azure.core.ResourceGroup("example", {
    location: "westeurope",
});
const exampleSqlServer = new azure.sql.SqlServer("example", {
    administratorLogin: "4dm1n157r470r",
    administratorLoginPassword: "4-v3ry-53cr37-p455w0rd",
    location: exampleResourceGroup.location,
    resourceGroupName: exampleResourceGroup.name,
    version: "12.0",
});
const exampleElasticPool = new azure.mssql.ElasticPool("example", {
    location: exampleResourceGroup.location,
    maxSizeGb: 756,
    perDatabaseSettings: {
        maxCapacity: 4,
        minCapacity: 0.25,
    },
    resourceGroupName: exampleResourceGroup.name,
    serverName: exampleSqlServer.name,
    sku: {
        capacity: 4,
        family: "Gen5",
        name: "GP_Gen5",
        tier: "GeneralPurpose",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-azurerm/blob/master/website/docs/r/mssql_elasticpool.html.markdown.

<h4 class="pdoc-member-header" id="ElasticPool-constructor">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L115"> <b>constructor</b></a>
</h4>


<pre class="highlight"><code><span class='kd'></span><span class='kd'>new</span> ElasticPool(name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, args: <a href='#ElasticPoolArgs'>ElasticPoolArgs</a>, opts?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions'>pulumi.CustomResourceOptions</a>)</code></pre>


Create a ElasticPool resource with the given unique name, arguments, and options.

* `name` The _unique_ name of the resource.
* `args` The arguments to use to populate this resource&#39;s properties.
* `opts` A bag of options that control this resource&#39;s behavior.

<h4 class="pdoc-member-header" id="ElasticPool-get">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L57">method <b>get</b></a>
</h4>


<pre class="highlight"><code><span class='kd'>public static </span>get(name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, id: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#ID'>pulumi.ID</a>&gt;, state?: <a href='#ElasticPoolState'>ElasticPoolState</a>, opts?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions'>pulumi.CustomResourceOptions</a>): <a href='#ElasticPool'>ElasticPool</a></code></pre>


Get an existing ElasticPool resource's state with the given name, ID, and optional extra
properties used to qualify the lookup.

<h4 class="pdoc-member-header" id="ElasticPool-getProvider">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L48">method <b>getProvider</b></a>
</h4>


<pre class="highlight"><code><span class='kd'></span>getProvider(moduleMember: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>): <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#ProviderResource'>ProviderResource</a> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span></code></pre>

<h4 class="pdoc-member-header" id="ElasticPool-isInstance">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L68">method <b>isInstance</b></a>
</h4>


<pre class="highlight"><code><span class='kd'>public static </span>isInstance(obj: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>): obj is ElasticPool</code></pre>


Returns true if the given object is an instance of ElasticPool.  This is designed to work even
when multiple copies of the Pulumi SDK have been loaded into the same process.

<h4 class="pdoc-member-header" id="ElasticPool-elasticPoolProperties">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L75">property <b>elasticPoolProperties</b></a>
</h4>

<pre class="highlight"><code><span class='kd'>public </span>elasticPoolProperties: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ElasticPoolElasticPoolProperties'>ElasticPoolElasticPoolProperties</a>&gt;;</code></pre>
<h4 class="pdoc-member-header" id="ElasticPool-id">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L48">property <b>id</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>id: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>Output</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#ID'>ID</a>&gt;;</code></pre>

id is the provider-assigned unique ID for this managed resource.  It is set during
deployments and may be missing (undefined) during planning phases.

<h4 class="pdoc-member-header" id="ElasticPool-location">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L79">property <b>location</b></a>
</h4>

<pre class="highlight"><code><span class='kd'>public </span>location: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</code></pre>

Specifies the supported Azure location where the resource exists. Changing this forces a new resource to be created.

<h4 class="pdoc-member-header" id="ElasticPool-maxSizeBytes">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L83">property <b>maxSizeBytes</b></a>
</h4>

<pre class="highlight"><code><span class='kd'>public </span>maxSizeBytes: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number'>number</a></span>&gt;;</code></pre>

The max data size of the elastic pool in bytes. Conflicts with `maxSizeGb`.

<h4 class="pdoc-member-header" id="ElasticPool-maxSizeGb">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L87">property <b>maxSizeGb</b></a>
</h4>

<pre class="highlight"><code><span class='kd'>public </span>maxSizeGb: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number'>number</a></span>&gt;;</code></pre>

The max data size of the elastic pool in gigabytes. Conflicts with `maxSizeBytes`.

<h4 class="pdoc-member-header" id="ElasticPool-name">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L91">property <b>name</b></a>
</h4>

<pre class="highlight"><code><span class='kd'>public </span>name: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</code></pre>

Specifies the SKU Name for this Elasticpool. The name of the SKU, will be either `vCore` based `tier` + `family` pattern (e.g. GP_Gen4, BC_Gen5) or the `DTU` based `BasicPool`, `StandardPool`, or `PremiumPool` pattern.

<h4 class="pdoc-member-header" id="ElasticPool-perDatabaseSettings">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L95">property <b>perDatabaseSettings</b></a>
</h4>

<pre class="highlight"><code><span class='kd'>public </span>perDatabaseSettings: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ElasticPoolPerDatabaseSettings'>ElasticPoolPerDatabaseSettings</a>&gt;;</code></pre>

A `perDatabaseSettings` block as defined below.

<h4 class="pdoc-member-header" id="ElasticPool-resourceGroupName">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L99">property <b>resourceGroupName</b></a>
</h4>

<pre class="highlight"><code><span class='kd'>public </span>resourceGroupName: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</code></pre>

The name of the resource group in which to create the elastic pool. This must be the same as the resource group of the underlying SQL server.

<h4 class="pdoc-member-header" id="ElasticPool-serverName">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L103">property <b>serverName</b></a>
</h4>

<pre class="highlight"><code><span class='kd'>public </span>serverName: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</code></pre>

The name of the SQL Server on which to create the elastic pool. Changing this forces a new resource to be created.

<h4 class="pdoc-member-header" id="ElasticPool-sku">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L107">property <b>sku</b></a>
</h4>

<pre class="highlight"><code><span class='kd'>public </span>sku: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ElasticPoolSku'>ElasticPoolSku</a>&gt;;</code></pre>

A `sku` block as defined below.

<h4 class="pdoc-member-header" id="ElasticPool-tags">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L111">property <b>tags</b></a>
</h4>

<pre class="highlight"><code><span class='kd'>public </span>tags: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;{[key: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>]: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>}&gt;;</code></pre>

A mapping of tags to assign to the resource.

<h4 class="pdoc-member-header" id="ElasticPool-urn">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L48">property <b>urn</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>urn: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>Output</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#URN'>URN</a>&gt;;</code></pre>

urn is the stable logical URN used to distinctly address a resource, both before and after
deployments.

<h4 class="pdoc-member-header" id="ElasticPool-zoneRedundant">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L115">property <b>zoneRedundant</b></a>
</h4>

<pre class="highlight"><code><span class='kd'>public </span>zoneRedundant: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span>&gt;;</code></pre>

Whether or not this elastic pool is zone redundant. `tier` needs to be `Premium` for `DTU` based  or `BusinessCritical` for `vCore` based `sku`. Defaults to `false`.


<h2 id="data-sources">Data Sources</h2>
<h3 class="pdoc-module-header" id="getElasticPool" data-link-title="getElasticPool">
    <a href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L29">
        Data Source <strong>getElasticPool</strong>
    </a>
</h3>


<pre class="highlight"><code><span class='kd'></span>getElasticPool(args: <a href='#GetElasticPoolArgs'>GetElasticPoolArgs</a>, opts?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions'>pulumi.InvokeOptions</a>): <a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise'>Promise</a>&lt;<a href='#GetElasticPoolResult'>GetElasticPoolResult</a>&gt; &amp; <a href='#GetElasticPoolResult'>GetElasticPoolResult</a></code></pre>


Use this data source to access information about an existing SQL elastic pool.

#### Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure from "@pulumi/azure";

const example = azure.mssql.getElasticPool({
    name: "mssqlelasticpoolname",
    resourceGroupName: "example-resources",
    serverName: "example-sql-server",
});

export const elasticpoolId = example.id;
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-azurerm/blob/master/website/docs/d/mssql_elasticpool.html.markdown.


<h2 id="apis">Others</h2>
<h3 class="pdoc-module-header" id="ElasticPoolArgs" data-link-title="ElasticPoolArgs">
    <a href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L227">
        interface <strong>ElasticPoolArgs</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kr'>interface</span> <span class='nx'>ElasticPoolArgs</span></code></pre>

The set of arguments for constructing a ElasticPool resource.

<h4 class="pdoc-member-header" id="ElasticPoolArgs-location">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L231">property <b>location</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>location?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</code></pre>

Specifies the supported Azure location where the resource exists. Changing this forces a new resource to be created.

<h4 class="pdoc-member-header" id="ElasticPoolArgs-maxSizeBytes">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L235">property <b>maxSizeBytes</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>maxSizeBytes?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number'>number</a></span>&gt;;</code></pre>

The max data size of the elastic pool in bytes. Conflicts with `maxSizeGb`.

<h4 class="pdoc-member-header" id="ElasticPoolArgs-maxSizeGb">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L239">property <b>maxSizeGb</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>maxSizeGb?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number'>number</a></span>&gt;;</code></pre>

The max data size of the elastic pool in gigabytes. Conflicts with `maxSizeBytes`.

<h4 class="pdoc-member-header" id="ElasticPoolArgs-name">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L243">property <b>name</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>name?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</code></pre>

Specifies the SKU Name for this Elasticpool. The name of the SKU, will be either `vCore` based `tier` + `family` pattern (e.g. GP_Gen4, BC_Gen5) or the `DTU` based `BasicPool`, `StandardPool`, or `PremiumPool` pattern.

<h4 class="pdoc-member-header" id="ElasticPoolArgs-perDatabaseSettings">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L247">property <b>perDatabaseSettings</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>perDatabaseSettings: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ElasticPoolPerDatabaseSettings'>ElasticPoolPerDatabaseSettings</a>&gt;;</code></pre>

A `perDatabaseSettings` block as defined below.

<h4 class="pdoc-member-header" id="ElasticPoolArgs-resourceGroupName">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L251">property <b>resourceGroupName</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>resourceGroupName: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</code></pre>

The name of the resource group in which to create the elastic pool. This must be the same as the resource group of the underlying SQL server.

<h4 class="pdoc-member-header" id="ElasticPoolArgs-serverName">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L255">property <b>serverName</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>serverName: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</code></pre>

The name of the SQL Server on which to create the elastic pool. Changing this forces a new resource to be created.

<h4 class="pdoc-member-header" id="ElasticPoolArgs-sku">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L259">property <b>sku</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>sku: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ElasticPoolSku'>ElasticPoolSku</a>&gt;;</code></pre>

A `sku` block as defined below.

<h4 class="pdoc-member-header" id="ElasticPoolArgs-tags">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L263">property <b>tags</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>tags?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;{[key: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>]: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>}&gt;;</code></pre>

A mapping of tags to assign to the resource.

<h4 class="pdoc-member-header" id="ElasticPoolArgs-zoneRedundant">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L267">property <b>zoneRedundant</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>zoneRedundant?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span>&gt;;</code></pre>

Whether or not this elastic pool is zone redundant. `tier` needs to be `Premium` for `DTU` based  or `BusinessCritical` for `vCore` based `sku`. Defaults to `false`.

<h3 class="pdoc-module-header" id="ElasticPoolState" data-link-title="ElasticPoolState">
    <a href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L180">
        interface <strong>ElasticPoolState</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kr'>interface</span> <span class='nx'>ElasticPoolState</span></code></pre>

Input properties used for looking up and filtering ElasticPool resources.

<h4 class="pdoc-member-header" id="ElasticPoolState-elasticPoolProperties">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L181">property <b>elasticPoolProperties</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>elasticPoolProperties?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ElasticPoolElasticPoolProperties'>ElasticPoolElasticPoolProperties</a>&gt;;</code></pre>
<h4 class="pdoc-member-header" id="ElasticPoolState-location">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L185">property <b>location</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>location?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</code></pre>

Specifies the supported Azure location where the resource exists. Changing this forces a new resource to be created.

<h4 class="pdoc-member-header" id="ElasticPoolState-maxSizeBytes">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L189">property <b>maxSizeBytes</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>maxSizeBytes?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number'>number</a></span>&gt;;</code></pre>

The max data size of the elastic pool in bytes. Conflicts with `maxSizeGb`.

<h4 class="pdoc-member-header" id="ElasticPoolState-maxSizeGb">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L193">property <b>maxSizeGb</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>maxSizeGb?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number'>number</a></span>&gt;;</code></pre>

The max data size of the elastic pool in gigabytes. Conflicts with `maxSizeBytes`.

<h4 class="pdoc-member-header" id="ElasticPoolState-name">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L197">property <b>name</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>name?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</code></pre>

Specifies the SKU Name for this Elasticpool. The name of the SKU, will be either `vCore` based `tier` + `family` pattern (e.g. GP_Gen4, BC_Gen5) or the `DTU` based `BasicPool`, `StandardPool`, or `PremiumPool` pattern.

<h4 class="pdoc-member-header" id="ElasticPoolState-perDatabaseSettings">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L201">property <b>perDatabaseSettings</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>perDatabaseSettings?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ElasticPoolPerDatabaseSettings'>ElasticPoolPerDatabaseSettings</a>&gt;;</code></pre>

A `perDatabaseSettings` block as defined below.

<h4 class="pdoc-member-header" id="ElasticPoolState-resourceGroupName">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L205">property <b>resourceGroupName</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>resourceGroupName?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</code></pre>

The name of the resource group in which to create the elastic pool. This must be the same as the resource group of the underlying SQL server.

<h4 class="pdoc-member-header" id="ElasticPoolState-serverName">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L209">property <b>serverName</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>serverName?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</code></pre>

The name of the SQL Server on which to create the elastic pool. Changing this forces a new resource to be created.

<h4 class="pdoc-member-header" id="ElasticPoolState-sku">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L213">property <b>sku</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>sku?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ElasticPoolSku'>ElasticPoolSku</a>&gt;;</code></pre>

A `sku` block as defined below.

<h4 class="pdoc-member-header" id="ElasticPoolState-tags">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L217">property <b>tags</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>tags?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;{[key: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>]: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>}&gt;;</code></pre>

A mapping of tags to assign to the resource.

<h4 class="pdoc-member-header" id="ElasticPoolState-zoneRedundant">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/elasticPool.ts#L221">property <b>zoneRedundant</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>zoneRedundant?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span>&gt;;</code></pre>

Whether or not this elastic pool is zone redundant. `tier` needs to be `Premium` for `DTU` based  or `BusinessCritical` for `vCore` based `sku`. Defaults to `false`.

<h3 class="pdoc-module-header" id="GetElasticPoolArgs" data-link-title="GetElasticPoolArgs">
    <a href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L49">
        interface <strong>GetElasticPoolArgs</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kr'>interface</span> <span class='nx'>GetElasticPoolArgs</span></code></pre>

A collection of arguments for invoking getElasticPool.

<h4 class="pdoc-member-header" id="GetElasticPoolArgs-name">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L53">property <b>name</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>;</code></pre>

The name of the elastic pool.

<h4 class="pdoc-member-header" id="GetElasticPoolArgs-resourceGroupName">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L57">property <b>resourceGroupName</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>resourceGroupName: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>;</code></pre>

The name of the resource group which contains the elastic pool.

<h4 class="pdoc-member-header" id="GetElasticPoolArgs-serverName">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L61">property <b>serverName</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>serverName: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>;</code></pre>

The name of the SQL Server which contains the elastic pool.

<h3 class="pdoc-module-header" id="GetElasticPoolResult" data-link-title="GetElasticPoolResult">
    <a href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L67">
        interface <strong>GetElasticPoolResult</strong>
    </a>
</h3>

<pre class="highlight"><code><span class='kr'>interface</span> <span class='nx'>GetElasticPoolResult</span></code></pre>

A collection of values returned by getElasticPool.

<h4 class="pdoc-member-header" id="GetElasticPoolResult-id">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L102">property <b>id</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>id: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>;</code></pre>

id is the provider-assigned unique ID for this managed resource.

<h4 class="pdoc-member-header" id="GetElasticPoolResult-location">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L71">property <b>location</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>location: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>;</code></pre>

Specifies the supported Azure location where the resource exists.

<h4 class="pdoc-member-header" id="GetElasticPoolResult-maxSizeBytes">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L75">property <b>maxSizeBytes</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>maxSizeBytes: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number'>number</a></span>;</code></pre>

The max data size of the elastic pool in bytes.

<h4 class="pdoc-member-header" id="GetElasticPoolResult-maxSizeGb">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L79">property <b>maxSizeGb</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>maxSizeGb: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number'>number</a></span>;</code></pre>

The max data size of the elastic pool in gigabytes.

<h4 class="pdoc-member-header" id="GetElasticPoolResult-name">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L80">property <b>name</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>;</code></pre>
<h4 class="pdoc-member-header" id="GetElasticPoolResult-perDbMaxCapacity">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L84">property <b>perDbMaxCapacity</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>perDbMaxCapacity: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number'>number</a></span>;</code></pre>

The maximum capacity any one database can consume.

<h4 class="pdoc-member-header" id="GetElasticPoolResult-perDbMinCapacity">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L88">property <b>perDbMinCapacity</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>perDbMinCapacity: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number'>number</a></span>;</code></pre>

The minimum capacity all databases are guaranteed.

<h4 class="pdoc-member-header" id="GetElasticPoolResult-resourceGroupName">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L89">property <b>resourceGroupName</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>resourceGroupName: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>;</code></pre>
<h4 class="pdoc-member-header" id="GetElasticPoolResult-serverName">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L90">property <b>serverName</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>serverName: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>;</code></pre>
<h4 class="pdoc-member-header" id="GetElasticPoolResult-tags">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L94">property <b>tags</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>tags: {[key: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>]: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>};</code></pre>

A mapping of tags to assign to the resource.

<h4 class="pdoc-member-header" id="GetElasticPoolResult-zoneRedundant">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-azure/blob/55a74dd194ca30db7d4741976e9c1f83f20b82f5/sdk/nodejs/mssql/getElasticPool.ts#L98">property <b>zoneRedundant</b></a>
</h4>

<pre class="highlight"><code><span class='kd'></span>zoneRedundant: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span>;</code></pre>

Whether or not this elastic pool is zone redundant.

