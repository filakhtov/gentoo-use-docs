# app-arch/file-roller

### libnotify
Pass the `-Dnotification=enabled` (`disabled` if the flag is disabled) option to the meson build command. Use the `libnotify` library to provide an ability to create desktop notifications, e.g. when archive creation is completed.

This flag should be enabled if desktop notifications are needed.

### nautilus
Pass the `-Dnautilus-actions=enabled` (`disabled` when the flag is disabled) option to the meson build command. Build and install Nautilus file manager plugin to integrate with file-roller. This provides context menu options for quickly creating or extracting archives.

This flag should only be enabled if the target system uses Nautilus as a file manager.
