# virtual/udev

### systemd
Use udev implementation provided by the [sys-apps/systemd](../sys-apps/systemd.md). When this flag is disabled, use the [sys-apps/systemd-utils](../sys-apps/systemd-utils.md) with the `udev` flag enabled or [sys-fs](../sys-fs/eudev.md) package instead.

This flag should only be enabled system-wide on systems that use systemd.
