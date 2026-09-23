# myproject
file integrity monitoring system
File Integrity Monitoring (FIM) System
A lightweight, Python-based File Integrity Monitoring (FIM) tool designed to track changes, additions, and deletions of files within a specified directory by utilizing cryptographic SHA-256 hashing.

Features
Baseline Generation: Scans a target directory recursively and records the cryptographic hash (SHA-256) of every file into a JSON baseline database.

Integrity Checking: Compares the current state of the monitored directory against the saved baseline to detect three core states:

Modified Files: Files whose contents (and consequently hashes) have changed.

Deleted Files: Files present in the baseline but missing from the directory.

New Files: Newly created or unauthorized files added to the monitored directory.

Efficient Chunked Reading: Reads large files in 4KB chunks during hash calculation to maintain a low memory footprint.

Project Structure
Plaintext
├── monitor.py          # Main script containing FIM logic
├── baseline.json       # Generated baseline storage file (created upon running option 1)
└── monitored_files/    # Target directory monitored for changes
