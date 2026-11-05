# Data contracts

[README](../README.md)

[Synthetic example](../examples/contract.json)

| Field | Illustrative JSON value type |
| --- | --- |
| `endpoint` | `str` |
| `input` | `dict` |
| `outcomes` | `list` |

The example is intentionally synthetic and is a documentation fixture, not a production schema. Empty, absent and unknown values must remain distinguishable. Validate structure at ingestion, normalize only after preserving the original meaning, and retain version and collection context for derived records. Error messages must not echo raw credentials or personal data.
