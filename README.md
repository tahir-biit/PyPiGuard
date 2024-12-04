# PypiGuard Dataset

A comprehensive dataset containing metadata about Python packages from the PyPI ecosystem. This dataset provides detailed information about package structure, size, API calls, and security classifications, making it valuable for research in software composition analysis, package security, and dependency management.

## Dataset Specifications

- Records: 6,669
- Columns: 11
- Format: CSV (UTF-8)
- Filename: `pypiguard_dataset.csv`

## Data Structure

| Column | Description |
|--------|-------------|
| group_ID | Unique identifier for package version and artifact type |
| ecosystem | Package ecosystem (PyPI) |
| scoped | Scoped namespaces indicator (optional) |
| package_name | Python package name |
| version | Package version |
| artifact_id | Package artifact type (e.g., tar-gz, whl) |
| total_file | Number of files in package |
| package_size | Package size in MB |
| api_calls | List of package API calls |
| function | Key package functions |
| threat_type | Package classification (benign/malicious) |

## Usage

```python
import pandas as pd
data = pd.read_csv('pypiguard_dataset.csv')
```

## Example Data

| group_ID | ecosystem | package_name | version | artifact_id | total_file | package_size | api_calls | function | threat_type |
|----------|-----------|--------------|---------|-------------|------------|--------------|------------|-----------|-------------|
| types-termcolor_1.1.6.2_tar-gz | pypi | types-termcolor | 1.1.6.2 | tar-gz | 11 | 6.67 MB | ['platform.system', 'urllib2.urlopen.read', 'requests.get', 'os.path.expanduser', 'os.chdir'] | init | benign |
| matplatlib-plus_1.1_tar-gz | pypi | matplatlib-plus | 1.1 | tar-gz | 8 | 0.85 MB | ['eval', 'eval', 'eval', 'eval', 'base64.b64decode', 'compile', 'eval'] | global | malicious |

## Data Quality Notes

- Missing data may occur in `scoped`, `api_calls`, and `function` columns
- Data cleaning may be required for specific analyses
- All sizes are in MB

## Research Applications

- Software composition analysis
- Package security assessment
- Dependency management research
- Malicious package detection
- API usage analysis
