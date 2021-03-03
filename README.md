# matomo-eb

[Matomo](https://matomo.org/) on [AWS Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/).

This repo contains `.ebextensions` and deploy hooks to install and configure Matomo, DBIP, and Cron.

## Prerequisites

1. Create a database for Matomo (e.g. Aurora MySQL).

## Setup

1. Configure non-sensitive variables in `config/config.ini.php`

2. Configure the following environment variables in your Elastic Beanstalk environment (required):

| Name | Example | Description |
| ---- | ------- | ----------- |
| `EMAIL` | `you@example.org` | Used in cron job |
| `URL` | `https://analytics.example.org` | URL to your Matomo domain, used in cron job |
| `MATOMO_DATABASE_HOST` | `xx.rds.amazonaws.com` | Hostname for your Matomo database |
| `MATOMO_DATABASE_USERNAME` | `matomo` | Username for your Matomo database |
| `MATOMO_DATABASE_PASSWORD` | `secret` | Password for your Matomo database |
| `MATOMO_DATABASE_DBNAME` | `matomodb` | Database name for your Matomo database |
| `MATOMO_GENERAL_SALT` | `abc123` | 32 character random string |
| `MATOMO_GENERAL_TRUSTED_HOSTS` | `"analytics.example.org", "xx.elasticbeanstalk.com"` | All allowed Matomo domains, comma-delimited with quotes |

## Contribute

Feel free to fork and improve!
