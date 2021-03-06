---
date: 2018-02-07T18:30:00+06:00
lastmod: 2018-02-09T17:00:00+06:00
title: Widgets
authors: ["muniftanjim"]
categories:
  - features
tags:
  - config
  - widgets
slug: widgets
toc: true
---
Minimo supports _**Widgets**_ that you can place on specific _**Widget Areas**_.

## Available Widgets

Minimo has the following built-in Widgets:

  Name             |  Slug
 ----------------- | -----------------
 1. About          | `about`
 2. Recent Posts   | `recent_posts`
 3. Taxonomy Cloud | `taxonomy_cloud`

### Widget Configuration Options

Here are the configuration options available for the Widgets:

#### Widget: About

- `about` [`Map`]:
  - `title` [`String`]: Title  
     _default: `.Site.Title`_
  - `description` [`String`]: Description  
    _default: `.Site.Params.info.description`_
  - `logo` [`String`]: path/url of Logo  
    _default: `"/images/logo.png"`_

#### Widget: Recent Posts

- `recentPosts` [`Map`]:
  - `title` [`String`]: Title  
    _default: `"Recent Posts"`_
  - `length` [`Integer`]: Number of posts to show  
    _default: `5`_
  - `excludeTypes` [`Array` of `String`s]:  Types of posts to exclude  
    _default: `["page"]`_

#### Widget: Taxonomy Cloud

- `taxonomyCloud` [`Map`]:
  - `title` [`String`]: Title  
    _default: Plural Name for `taxonomyCloud.taxonomy`_
  - `taxonomy` [`String`]: Taxonomy to show  
    _default: `.Site.Params.info.description`_
  - `shuffle` [`Boolean`]: Shuffle Taxonomy Terms  
    _default: `true`_

## Available Widget Areas

  Name    |  Slug
 -------- | ----------
 Homepage | `homepage`
 Sidebar  | `sidebar`

You can add Widgets to Widget Areas from your **`config.toml`** file:

```toml
[params.widgets]
homepage = ["recent_posts"]
sidebar = ["about","taxonomy_cloud"]
```

The syntax for adding Widgets to Widget Areas is:

```toml
widget_area_slug = [ widget_slug_1, widget_slug_2, ...]
```

## Widgets Configuration File

Minimo picks up Widgets' configuration from the **`/data/config/widgets.toml`** file.

Here's the _Widgets Config file_ for this site:

**`/data/config/widgets.toml`**

{{< file "data/config/widgets.toml" >}}

If configuration for any Widgets are missing in this file, Minimo will fallback to the default configuration for those Widgets.

Go wild!
