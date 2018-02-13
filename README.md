[![Build status](https://travis-ci.org/rocketsciencesolutions/wordpress-collect.svg?branch=master)](https://travis-ci.org/rocketsciencesolutions/wordpress-collect)
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/rocketsciencesolutions/wordpress-collect/elements/wordpress-collect)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](http://standardjs.com)

# \<wordpress-collect\>

The `wordpress-collect` element makes it possible to interact with the native [WP REST API](https://developer.wordpress.org/rest-api/reference/).

## Table of Contents
1 [Install the element in your project](#installation)<br/>
2 [Usage](#usage)<br/>
      2.1 [Attribute: base-url - required](#base-url)<br/>
      2.2 [Attribute: resource - required](#resource)<br/>
      2.3 [Attribute: id - optional](#id)<br/>
      2.4 [Attribute: response - required](#response)<br/>
      2.5 [Attribute: wp-api-url - optional](#wp-api-url)<br/>

<a name="installation"></a>
## 1 Installation

```bash
bower install --save wordpress-posts
```

<a name="usage"></a>
## 2 Usage 

```html
<wordpress-collect
      base-url="https://yourwordpressurl.com"
      resource="pages"
      response="{{wpPages}}"></wordpress-collect>

<template
      is="dom-repeat"
      items="[[wpPages]]"
      as="page">
      <div>
            <h1>[[page.title.rendered]]</h1>
            <div>[[page.content.rendered]]</div>
      </div>
</template>
```

<a name="base-url"></a>
### 2.1 base-url - required
The required `base-url` attribute is the Wordpress url you want to retrieve the data from.

<a name="resource"></a>
### 2.2 resource - required
The required `resource` attribute indicates the kind of resource to retrieve. This can be pages | posts or other resources defined in the [WP REST API reference](https://developer.wordpress.org/rest-api/reference/).

<a name="id"></a>
### 2.3 id - optional
The optional `id` attribute can be set to request a specific data object, like a page with the id 5.

<a name="response"></a>
### 2.4 response - required
When data is received the binding in the `response` attribute is updated with the retrieved data and available for use in the component which `wordpress-collect` is situated.

<a name="wp-api-url"></a>
### 2.5 wp-api-url - optional
Optionally you can set the `wp-api-url` attribute. When not defined it will always default to `wp-json/wp/v2`, which is the default WP REST API segment. The `wp-api-url` attribute will be appended to the `base-url`.