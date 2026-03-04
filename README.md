# Status

So far this just installs the `gitlab-common` package.  More to follow.

# BUGS

This role needs the platform role `debian-fasttrack` to make the
`gitlab-common` package available.  Currently platform roles must be declared
in host variables.  Ideally, this role would depend on `debian-fasttrack`, but
unless the host variables declare all the platform roles, repo configuration
may not be updated correctly during major OS upgrades.  For the moment, this
role should simply fail unless `debian-fasttrack` is declared as a platform
role in the relevant host variables.  (Platform roles are expected to be pulled
in by `automatic-updates`, not deployed alone.)
