# Upload Instructions

This ZIP contains a documentation package intended for the existing repository:

https://github.com/naph1/Security-Onion-SOC-Lab

## Before uploading

1. Extract the ZIP.
2. Review the README and every report for accuracy.
3. Confirm that the reconstructed SSH investigation wording reflects what you are comfortable claiming.
4. Keep the provenance disclaimer. Do not add fabricated IPs, timestamps, alert IDs, commands, event counts, or screenshots.
5. If you have the actual three portfolio screenshot image files, you may add them to `evidence/` using the filenames documented in `evidence/README.md`. The current ZIP links to the published portfolio images and does not pretend to contain local copies.

## Upload

Copy the contents of the extracted `Security-Onion-SOC-Lab-Upload` folder into the root of the existing GitHub repository, preserving the folder structure. The package includes a replacement README and `.gitignore` / `.gitattributes`.

When GitHub asks whether to replace the existing README or metadata files, review the diff before confirming. Do not delete unrelated existing repository content.

Suggested commit message:

`Add SOC lab documentation and SSH investigation report`

## Important

This package is documentation only. It does not contain VM images, original PCAPs, raw event records, or configuration exports. It does not modify or publish the GitHub repository automatically.
