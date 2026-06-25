# Dataset Pair Patcher

A robust, safety-first utility to identify, isolate, and track unpaired files between two corresponding dataset directories.

## Description
When creating synthetic supervised learning datasets, some images may fail to process, resulting in broken pairs between source directories. This tool ensures your data remains clean by validating that corresponding subdirectories have matching file stems. It identifies files that lack a counterpart, moves them to a separate 'unpaired' directory, and maintains a strict audit trail of every change.

## Features
- **Dynamic Pairing:** Automatically aligns and pairs corresponding subdirectories using sorted matching logic.
- **Safety First:** Uses a "Copy-Verify-Delete" workflow. Files are moved, verified, and audited—never deleted without your explicit confirmation.
- **Audit Trail:** Generates an `unpaired_manifest.json` file, providing a transparent, machine-readable record of all operations.
- **Efficient Processing:** Uses hash-map dictionary lookups for instant file identification, allowing for high performance even with large datasets.

## How to Use
1. **Configure:** Update the source and destination directory paths in the script.
2. **Process:** Run the main processing function to identify unpaired files. They will be copied to a local `/unpaired` directory for your review.
3. **Verify:** Inspect the generated `unpaired_manifest.json` and the files in the `/unpaired` folder to ensure accuracy.
4. **Cleanup:** Once satisfied, run the cleanup function to safely remove the original unpaired files from your source directories.

## Safety Note
This tool is designed to prevent accidental data loss. Always verify the contents of the 'unpaired' directory before running the final cleanup function.
