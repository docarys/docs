## About configuration file

The configuration file, docarys.yml, is located at project root folder.

Remember, this configuration parameters has effect in both the general behaviour of Docarys (e.g. the output folder), but also in the theme (e.g. site name, description, author, theme...)

## Configuration parameters

This is the list of default parameters that can be used with docarys and material for docarys. New paramteres can be added when customizing the theme. 

All configuration paramteres is sent to the them renderer, so they are effectively available once added to docarys.yml

!!! warning Live server reload known issue
At the moment, changes in docarys.yml are not being tracked by the live server. To see changes applied to docyars.yml, please stop and serve again.
!!!


| Paramater name            | Short description                               | Required | Default    |
| ------------------------- | ----------------------------------------------- | -------- | -----------|
| site_name                 | Documentation site name                         | Yes      |            |
| pages                     | Array with the site's page tree structure       | No       | `null`     |
| meta.description          | A brief description of the site                 | No       | `null`     |
| meta.author               | Site author information                         | No       | `null`     |
| site_url                  | Canonical URL of the site                       | No       | `null`     |
| repo_url                  | Links the documentation site to a SCM           | No       | `null`     |
| repo_name                 | Repository name in the SCM                      | No       | `null`     |
| edit_uri                  | Absolute base path where the edit page is found | No       | `null`     |
| copyright                 | Site copyright information                      | No       | `null`     |
| google_analytics          | Google analystics tracking identifier           | No       | `null`     |
| theme.name                | Docarys theme that should be used               | No       | `material` |
| theme.language            | Theme language                                  | No       | `en`       |
| theme.feature.tabs        | Enables or disables the 'tabs' feature          | No       | `false`    |
| theme.palette.primary     | Palette primary color (Material theme only)     | No       | `null`     |
| theme.palette.accent      | Palette accent color (Material theme only)      | No       | `null`     |
| theme.font.text           | Site font for text                              | No       | `null`     |
| theme.font.code           | Font used in the fenced code blocks             | No       | `null`     |
| theme.favicon             | Site favicon resource relative URI              | No       | `null`     |
| extra.social              | Array of social objects (type and link)         | No       | `null`     |

### site_name

| Required | Default value |
| -------- | ------------- |
| Yes      |               |

Documentation site name. By default, this parameter is used as website title and as page metadata.

Configuration example:

!!! example Example

``` yml
name: Docarys documentation website
```

!!!

### pages

| Required | Default value |
| -------- | ------------- |
| No       |               |

This configuration property contains an object array, describing site's page tree structure. Docarys will walk the tree in the described order, creating all the page metadata and links required.

!!! tip Take control of your website structure with "pages"
This parameter is not mandatory. However, it is highly recommended to create the title and file association in the configuration file. Otherwise, docarys will use the disk tree structure to create the website, and you'll miss control over important things, like order or page title.
!!!

!!! example Example

``` yml
pages:
  - Docarys:
    - Home: index.md
    - Installation: docarys/installation.md
    - Configuration: docarys/configuration.md
    - Get started: docarys/get-started.md
    - License: license.md
  - Material for Docarys:
      - Index: material/index.md
```

!!!

### meta.description

| Required | Default value |
| -------- | ------------- |
| No       | `null`        |

This parameter is used, by default in Material for Docarys, to add the metadata "dsecription" in the page header.

It is also possible to configure this meta header using the `site_description` configuration, inherited from MKDocs for backward compatibility. However, if you are migrating from MKDocs to docarys, is highly recommeded to use docarys notation

!!! example Example

``` yml
meta:
  description: Yet another static web site utility for technical documentation.
```

!!!

### meta.author

| Required | Default value |
| -------- | ------------- |
| No       | `null`        |

This parameter is used, by default in Material for Docarys, to add the metadata "author" in the page header.

It is also possible to configure this meta header using the `site_author` configuration, inherited from MKDocs for backward compatibility. However, if you are migrating from MKDocs to docarys, is highly recommeded to use docarys notation

!!! example Example

``` yml
meta:
  author: Sergio Sisternes
```

!!!

### site_url

| Required | Default value |
| -------- | ------------- |
| No       | `null`        |

Canonical URL where this documentation site is found.

By default, Material for docarys uses it to create a link from the header logo to the main docs page.

!!! example Example

``` yml
site_url: http://docs.docarys.io
```

!!!

### repo_name

| Required | Default value |
| -------- | ------------- |
| No       | `null`        |

When set, instructs docarys which repository is linked to this project, displaying the name and stastics accordingly.

!!! note Note

The intent for this property is to point where your project source code is. Not where the documentation source is. This way, if your code is hosted in Github, docarys will display your project statics (starts and forks), instead of the documenation ones.

!!!

!!! example Example

``` yml
repo_name: docarys/docarys
```

!!!

### repo_url

| Required | Default value |
| -------- | ------------- |
| No       | `null`        |

When set, instructs docarys which SCM repository should by linked with this documentation site. This URL can be different from the documentation SCM repository.

!!! note Note

The intent for this property is to point where your project source code is. Not where the documentation source is. This way, if your code is hosted in Github, docarys will display your project statics (starts and forks), instead of the documenation ones.

!!!

!!! example Example

``` yml
repo_url: https://github.com/docarys/docarys
```

!!!

### edit_url

| Required | Default value |
| -------- | ------------- |
| No       | `null`        |

When set, edit_url indicates docarys where the actual markdown pages can be edited. Docarys expects a Canonical URL to the root SCM repository. Docarys will complete the edit route automatically, making a concatenaton of edit_url and the page it is rendering. You can give a try to this features by clicking the "pencil" icon you can find in the top of this page.

!!! note Note

The intent for this property is to point where your documentation source code is.

!!!

!!! example Example

``` yml
edit_uri: https://github.com/docarys/docs/blob/master
```

!!!

### copyright

| Required | Default value |
| -------- | ------------- |
| No       | `null`        |

Copyright information to be included in the site.

!!! example Example

``` yml
copyright: 'Copyright &copy; 2017 - 2018 Sergio Sisternes'
```

!!!

### google_analytics

| Required | Default value |
| -------- | ------------- |
| No       | `null`        |

When specified, adds the google analytics tracking configuration to the page.

!!! example Example

``` yml
copyright: 'Copyright &copy; 2017 - 2018 Sergio Sisternes'
```

!!!

## Support Source Control Management systems

The following SCM tools are supported by docarys out of the box:

| SCM          |
| ------------ |
| Gihub        |
| Gitlab       |
| Bitbucket    |
| Other Git    |

!!! note About other Git servers
Using other Git servers/services is possible. However, the theme won't provide you the logo or other repository information.
!!!