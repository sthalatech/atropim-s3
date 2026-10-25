# atropim-s3-storage

S3-compatible object storage backend for AtroPIM / AtroCore file and media storage, configured entirely through AtroCore's native Admin panel.

## Install

```json
{
    "repositories": [
        { "type": "vcs", "url": "https://github.com/sthalatech/atropim-s3-storage" }
    ],
    "require": {
        "sthalatech/atropim-s3-storage": "^1.0"
    }
}
```

Add this to your AtroPIM installation's root `composer.json`, then run `php composer.phar update` (AtroCore's embedded Composer, as the same user your web server runs as). Requires AtroCore `>=2.3.4`, PHP `>=8.4`, and an S3 or S3-compatible bucket (MinIO, Cloudflare R2, Wasabi, etc.).

## Usage

Configure via **Administration → Connections** (S3 credentials/endpoint) and **Administration → Storages** (links to a Connection, optional key prefix), then assign the Storage to a Folder. Uploads to that folder now land in S3; existing files elsewhere are unaffected.

See [PLAN.md](PLAN.md) for the full design rationale, including IAM-role authentication, backend compatibility, and known limitations.

## Contributing

Issues and PRs are welcome. For significant changes, please open an issue first to discuss what you'd like to change.

## Reporting Issues

Found a bug or have a feature request? [Open an issue](../../issues/new) with steps to reproduce (or the use case, for feature requests).

## License

GPL-3.0 © Sthala
