# VyHub Import/Export

The VyHub import can be used to import/export the database of your VyHub instance.

There are the following limitations:

- Exported archives can only be imported into the same VyHub version
- Exports from a VyHub instance cannot be imported into a different Cloud instance

> If you encounter problems during the export (e.g. Network Errors) please contact the support.

**Important:** When transferring the database between different VyHub instances (e.g. from Cloud to Self-Hosting), you need to update the `VYHUB_CRYPT_SECRET` environment variable in `.env`.
The new secret will be displayed after the import has been finished or can also be extracted from the exported zip archive (`manifest.json`).