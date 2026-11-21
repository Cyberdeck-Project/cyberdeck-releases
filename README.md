# cyberdeck-releases

This public repository hosts the encrypted, signed update packages used by installed Cyberdeck for Windows apps. Cyberdeck checks this feed and verifies each package before installing it; users do not need a GitHub account for in-app updates.

This repository is the update feed, not the installer download or source-code repository. New users get the one-file installer from the private, invite-only [Cyberdeck Installer releases](https://github.com/Cyberdeck-Project/cyberdeck-installer/releases).

Each update version uses `Cyberdeck-Application-Update-<version>.cybenc` with a matching `Cyberdeck-Application-Update-<version>.cybenc.sig` signature. GitHub Actions in the private application source repository publishes these files. Do not manually replace or mix packages and signatures.

See [FILE-GUIDE.md](FILE-GUIDE.md) for the tracked-file inventory.

The release assets are generated as matched payload/signature pairs. Keep each exact pair together; the installed client verifies the detached signature before using a package. See [central project guidance](https://github.com/Cyberdeck-Project/cyberdeck-project-guidance/blob/main/AGENTS.md) and [FILE-GUIDE.md](FILE-GUIDE.md).
