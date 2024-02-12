## Specifications for UNCA
This document covers standards, practises and documentation for UNCA, both for its initial development and as a guide for creating apps using the standard.

### Preamble
If you've read a OPENSPEC document before you can skip this part.
- Communication is documented from the perspective of the client unless specified otherwise
- Data is represented by JSON/BSONs with comments for clarity of specifics (e.g. u16 instead of u32).
- Data {surrounded by brackets} represent variables and UPPERCASE represent constants.
- When documenting interactions the standard follows "Collection; Action". for example Message; Send.
- If an item in the JSON has the nullable* comment it means that at least ONE of the nullable* fields MUST be present.
- Guidelines recommend abiding by CRUD order and wording
