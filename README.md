# Status

Currently this role installs the package but does not apply any configuration or start any services.

# To Do

* Integrate with nginx.
* Configure details like hostname, as mentioned in the official instructions.
* Document post install steps like setting a root password.  (Gitlab root, not system root.)
* Choose a server and assign it the gitlab role.
* Configure backup for the chosen gitlab server.

# Description

This package installs gitlab, specifically the Community Edition (not
Enterprise Edition), from the gitlab.com repo, to a Debian host.

[Official
instructions](https://docs.gitlab.com/install/package/debian/?tab=Community+Edition)
link to an [installation
script](https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh) which seems to pull from the web both [apt configuration (trixie linked)](https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/config_file.list?os=debian&dist=trixie&source=script) and a [package signing key](https://packages.gitlab.com/gitlab/gitlab-ce/gpgkey).  This role should configure that repo without the need to run that script.

