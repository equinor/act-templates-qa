---
name: SSL Certificate Renewal
about: Issue template for renewing SSL Certificates
title: 'chore: renew ssl certificate for domain.equinor.com'
labels: 'ssl-certificate'
assignees: ''
---

## Description

Renew SSL Certificate for `<DOMAIN>`.equinor.com

The SSL Certificate contains the following entries:

- `<DOMAIN>`.equinor.com

## App Service using the certificate

The following App Service is using the SSL Certificate:

| App Service | Custom Domain | Resource Group |
|--|--|--|
| [app-service-name](URL) | `<DOMAIN>`.equinor.com | [resource-group](URL) |

## Key Vaults where SSL Certificate is imported

The following Key Vaults have SSL Certificate imported:

| Key Vault | Resource Group |
|--|--|
| [key-vault](URL) | [resource-group](URL) |

## SSL Certificate in Key Vaults

The following SSL Certificates are available in the Key Vaults:

| Certificate Name | Key Vault |
|--|--|
| [certificate-name](URL) | [key-vault](URL) |

## Service Now RITMs

| Year | RITM |
|--|--|
| 2022 | [RITMXXXXXXX](https://equinor.service-now.com/nav_to.do?uri=sc_req_item.do?sys_id=) |
| 2023 | [RITMXXXXXXX](https://equinor.service-now.com/nav_to.do?uri=sc_req_item.do?sys_id=) |

## Service Now input

The following information was used for last RITM in Service Now when ordering certificate:

- **WBS**: `<WBS_INFORMATION>`
- **Title**: Renew SSL Certificate for `<DOMAIN>`.equinor.com
- **Equinor responsible (approver and contact person)**: `<EQUINOR_RESPONSIBLE>`
- **Certificate name (E.g. www.statoil.com)**: `<DOMAIN>`.equinor.com
- **New certificate or renewal**: Renewal

## Tasks

- [ ] Generate CSR
- [ ] Request [Public SSL certificate](https://equinor.service-now.com/selfservice/?id=sc_cat_item&sys_id=2c2dbdf16fdb9100a7c62dc71e3ee417) in Service Now
- [ ] Convert PEM to PFX with Export secret
- [ ] Add Export secret to [key-vault](URL)
- [ ] Upload the certificate in Key Vault [key-vault](URL)
- [ ] Import certificate on App Service [app-service-name](URL)
- [ ] Set correct binding for imported certificate if not updated after importing
- [ ] Verify Certificate has been updated properly on App Services
- [ ] Disable previous versions of Key Vault Certificates after verification
- [ ] Remove old, expired SSL Certificate on App Service
