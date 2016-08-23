# shinken-pack-collectd-php-fpm

## Description

This Shinken monitoring pack is used to manage php-fpm services with our
standard deployment of Collectd.

We request Collectd data using unixsock plugin and collectd-nagios script from
collecd-utils package.

This pack depends to shinken-pack-collectd-base to work

## Objects

### Templates

#### Host templates

* collectd-php-fpm: Manage all default thresholds and values for services

### Services

| Service name              | Description             | Value specification                            | DS        | Consolidation | Warning variable | Critical variable | Duplicate_foreach variable |
|---------------------------|-------------------------|------------------------------------------------|-----------|---------------|------------------|-------------------|----------------------------|
| PHP-FPM - $KEY$ processes | Check php-fpm processes | processes-$VALUE1$/ps_count                    | processes | none          | $VALUE2$         | $VALUE3$          | _php_fpm_processes         |

## Default values

    _php_fpm_processes    Master $(php-fpm: master)$$(1:1)$$(1:1)$,www pool $(php-fpm: pool www)$$(1:)$$(1:)$
