# Twintip Schema Discovery for Spring Web

[![Build Status](https://img.shields.io/travis/zalando-stups/twintip-spring-web/master.svg)](https://travis-ci.org/zalando-stups/twintip-spring-web)
[![Coverage Status](https://img.shields.io/coveralls/zalando-stups/twintip-spring-web/master.svg)](https://coveralls.io/r/zalando-stups/twintip-spring-web)
[![Javadoc](https://javadoc-emblem.rhcloud.com/doc/org.zalando/twintip-spring-web/badge.svg)](http://www.javadoc.io/doc/org.zalando/twintip-spring-web)
[![Release](https://img.shields.io/github/release/zalando-stups/twintip-spring-web.svg)](https://github.com/zalando-stups/twintip-spring-web/releases)
[![Maven Central](https://img.shields.io/maven-central/v/org.zalando/twintip-spring-web.svg)](https://maven-badges.herokuapp.com/maven-central/org.zalando/twintip-spring-web)
[![License](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://raw.githubusercontent.com/zalando-stups/twintip-spring-web/master/LICENSE)

Twintipify your Spring Web MVC application. This library exposes all the endpoints TWINTIP requires.
See the documentation for [TWINTIP](http://stups.readthedocs.org/en/latest/components/twintip.html).

## Usage

First make sure that the endpoints are mapped into your application.

```java
import org.zalando.twintip.spring.SchemaResource;

@Configuration
@Import(SchemaResource.class)
public class YourConfigration {
    // whatever you configure
}
```

Next you need to provide the API definition and decide where clients should find it.
You can do this in your *application.properties* or [*application.yml*](http://docs.spring.io/spring-boot/docs/current/reference/html/boot-features-external-config.html#boot-features-external-config-yaml).

```yaml
twintip:
  mapping: /api
  yaml: "classpath:api.yml"
```

You are done.

## Other options

SchemaResource will send CORS Access-Control-* headers by default. You can disable this by setting twintip.cors property to false.

Host, port, schemes and basePath inside of the API definition can be overridden by setting property twintip.baseUrl to full base URL of API.
