# Validation strategy

[README](../README.md)

| Scenario | Expected behavior |
| --- | --- |
| Missing session | Reject before opportunity or application data is returned |
| Base change | Return conflict rather than replace the existing binding |
| Real receiving disabled | Return unavailable; never imply documents were stored |
| Invalid document metadata | Reject unsupported size, type or missing required document |

## Evidence policy

Record the revision, environment, input class, expected outcome and observed outcome for each executed check. Keep planned scenarios separate from measured results. The private backup service tests and public documentation checks do not certify product readiness, campaign results or production security.
