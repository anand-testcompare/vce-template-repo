# S3 Bucket Exploration Tool

## Overview
A Python script for security reconnaissance of publicly accessible S3 buckets. Given any S3 URL (typically a deep path to a specific file), this tool systematically explores parent directories to discover what content is publicly exposed.

## Use Case
**Scenario**: You find a single file URL like `https://company-data.s3.amazonaws.com/reports/2024/sensitive-document.pdf` and want to understand what else might be publicly accessible in the bucket structure.

**What it does**: Steps back through URL paths (`/reports/2024/` → `/reports/` → `/`) to enumerate all publicly listable content at each level.

## Installation & Usage

### Quick Start
```bash
python3 explore_s3_path.py "https://bucket-name.s3.amazonaws.com/path/to/file.ext"
```

### Example
```bash
python3 explore_s3_path.py "https://m-library.s3.amazonaws.com/ASCO/UCSF%20ASCO%20GU.pdf"
```

## Output Format
```
Exploring bucket: m-library
Starting path: ASCO/UCSF%20ASCO%20GU.pdf

============================================================
Listing: ASCO/
============================================================

Directories:
  📁 ASCO/internal-docs/
  📁 ASCO/presentations/

Files:
  📄 ASCO/financial-report.pdf (5.23 MB)
  📄 ASCO/strategy-2024.docx (1.45 MB)

============================================================
Listing: (root)
============================================================

Directories:
  📁 confidential/
  📁 employee-data/
  📁 financial-records/
```

## Features
- **Automatic URL parsing** - Handles both `bucket.s3.amazonaws.com` and `s3.amazonaws.com/bucket` formats
- **Path traversal** - Systematically explores from deep paths back to root
- **Content categorization** - Separates directories from files with size information
- **Limited output** - Shows first 20 items per category to avoid overwhelming output
- **Error handling** - Gracefully handles access denied and malformed URLs

## Security Considerations
This tool is designed for **defensive security purposes only**:
- Identifying misconfigured public S3 buckets in your organization
- Security auditing of your own infrastructure
- Understanding exposure scope when investigating data leaks
- Educational purposes for security awareness

**Important**: Only use on buckets you own or have explicit permission to test.

## Technical Details
- Uses S3 XML API for bucket listing
- Handles URL encoding for special characters
- Parses XML responses to extract object keys and metadata
- No authentication required (public buckets only)

## Dependencies
```bash
pip install requests
```

## Common S3 URL Formats Supported
- `https://bucket-name.s3.amazonaws.com/path/file.ext`
- `https://s3.amazonaws.com/bucket-name/path/file.ext`
- `https://bucket-name.s3.region.amazonaws.com/path/file.ext`

## Limitations
- Only works with publicly listable S3 buckets
- Limited to 1000 objects per directory listing
- Does not attempt to access private objects
- XML parsing may fail on very large bucket listings