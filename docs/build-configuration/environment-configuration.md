---
layout: "docs"
title: Environment Configuration
class: documentation
permalink: /build/environment-configuration/
published: true
---

You have access to certain environment options while configuring your Probo builds. These options are set as top level keys, on the same level as `assets` or `steps` in your `probo.yaml` file.

## Image

You can select which Docker image you want your environments to use.

{% highlight yaml %}
image: proboci/ubuntu-14.04-lamp:php-5.6
{% endhighlight %}

### Available Images

* `proboci/ubuntu-14.04-lamp:php-5.6`
* `proboci/ubuntu-14.04-lamp:php-7.0`
* `proboci/ubuntu-14.04-lamp:php-7.1`


## Allow Environment Access While Building

We assume environments have confidential data and can be in potentially insecure or unstable states while building. Because of this, our default settings make sure environments are not made public until all of the steps have completed and the build is finished.

Setting the `allowAccessWhileBuilding` configuration flag to true allows access to the environment while building. This configuration variable can be used in combination with the `$BUILD_URL` environment variable to make your site available to external services and to kick them off in build steps.

{% highlight yaml %}
allowAccessWhileBuilding: true
{% endhighlight %}

## Basic Environment Authentication

You can set up basic authentication for your Probo environments with `basicAuth`. This will require users to enter the correct username and password to access the Probo site.

{% highlight yaml %}
basicAuth:
  username: foo
  password: bar
{% endhighlight %}