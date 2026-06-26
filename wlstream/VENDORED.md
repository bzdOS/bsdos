# Vendored copy — github.com/bzdOS/WLStream

This directory is a **vendored snapshot** of the WLStream crate.

- Canonical upstream: https://github.com/bzdOS/WLStream
- Local git repo: `/root/wlstream` (separate, do not rm)
- Reason for vendoring: VM 185 mounts only `/root/bsdOS` via 9p → `/mnt/bsdos`.
  `cargo build` on VM cannot reach `/root/wlstream`. Vendoring fixes the build path.

## To sync from upstream

```sh
rsync -a --delete --exclude='.git' /root/wlstream/ /root/bsdOS/wlstream/
rm -f /root/bsdOS/wlstream/VENDORED.md   # preserve this file
# then re-add VENDORED.md and commit
```

Do NOT edit this copy directly for feature work — edit `/root/wlstream`, test there,
then sync here and commit both.
