# Status

This role should install the `gitlab` package, when that package is available
in the Debian fasttrack and/or backports-staging repo corresponding to the
current release.

2026-03-04:  Currently the package is not available for the `trixie` (stable).
This role may work if deployed to a host still running `bookworm` (oldstable).
I explored the option of adjusting apt pin priorities and allowing installation
of packages from oldstable, but major packages like `libssl` would need to be
downgraded, breaking other dependencies.


# BUGS

This role needs the platform role `debian-fasttrack` to make the
`gitlab-common` package available.  Currently platform roles must be declared
in host variables.  Ideally, this role would depend on `debian-fasttrack`, but
unless the host variables declare all the platform roles, repo configuration
may not be updated correctly during major OS upgrades.  For the moment, this
role should simply fail unless `debian-fasttrack` is declared as a platform
role in the relevant host variables.  (Platform roles are expected to be pulled
in by `automatic-updates`, not deployed alone.)
