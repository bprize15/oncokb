# Enhanced Variant Search with Genomic Coordinates

## What's New

Added support for searching variants using genomic coordinates in addition to HGVS nomenclature. The API now accepts genomic position queries with chromosome, start, end, and allele information. This improves discoverability for users working with raw sequencing data who may not have HGVS annotations readily available.

## Impact

- Researchers and bioinformatics teams can now query OncoKB variants directly using genomic coordinates
- Reduces the need for coordinate-to-HGVS conversion workflows before searching
- No breaking changes to existing API endpoints or behavior

## API Changes

- **Added** `GET /api/v1/variants/genomic` - New endpoint to search variants by genomic coordinates
  - Parameters: `chromosome`, `start`, `end`, `referenceAllele`, `alternateAllele`
  - Returns standard variant response objects

- **Added** `x-genomic-coordinate` optional parameter to existing search endpoints for compatibility

## Migration / Action Required

None. This is a new feature that does not affect existing integrations.

## Related Links

- [Issue #8765](https://github.com/oncokb/oncokb/issues/8765) - Feature request for genomic coordinate search
- [Documentation PR](https://github.com/oncokb/oncokb-docs/pull/234) - Updated API docs
