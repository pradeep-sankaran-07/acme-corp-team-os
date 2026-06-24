# Customers

One place for customers and prospects, distinguished by stage. Source of truth is the CRM (see `../config.yaml`). The daily routine only touches customers on the watch list.

## Active
| Customer | Owner | Domain | Health | Folder |
| --- | --- | --- | --- | --- |
| Northwind Software | Sam Okafor | northwindsoftware.com | green | northwind-software/ |
| Brightwave Media | Sam Okafor | brightwavemedia.com | amber | brightwave-media/ |

## Onboarding
| Customer | Owner | Domain | Folder |
| --- | --- | --- | --- |
| Vertex Analytics | Sam Okafor | vertexanalytics.io | vertex-analytics/ |

## Prospects
| Customer | Owner | Domain | Folder |
| --- | --- | --- | --- |
| Cobalt Security | Lena Vossen | cobaltsecurity.com | cobalt-security/ |

To add a customer: copy `_template/` to `customers/<slug>/`, fill `profile.md`, and add it to the watch list in `config.yaml`.
