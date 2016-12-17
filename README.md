# NAME

Zabbix::Check - Zabbix checks

# VERSION

version 1.01

# SYNOPSIS

Zabbix checks

# USAGE

## Disk

### zabbix\_agentd.conf

`
UserParameter=cpan.zabbix.check.disk.discovery,/usr/bin/perl -MZabbix::Check::Disk -e_discovery
UserParameter=cpan.zabbix.check.disk.bps[*],/usr/bin/perl -MZabbix::Check::Disk -e_bps $1 $2
UserParameter=cpan.zabbix.check.disk.iops[*],/usr/bin/perl -MZabbix::Check::Disk -e_iops $1 $2
UserParameter=cpan.zabbix.check.disk.ioutil[*],/usr/bin/perl -MZabbix::Check::Disk -e_ioutil $1 $2`

> **$1** Device name eg: sda, sdb1, dm-3, ...
>
> **$2** Type: read or write or total

# INSTALLATION

To install this module type the following

        perl Makefile.PL
        make
        make test
        make install

from CPAN

        cpan -i Zabbix::Check

# DEPENDENCIES

This module requires these other modules and libraries:

- Switch
- FindBin
- Cwd
- File::Basename
- File::Slurp
- JSON

# AUTHOR

Orkun Karaduman &lt;orkunkaraduman@gmail.com&gt;

# COPYRIGHT AND LICENSE

Copyright (C) 2016  Orkun Karaduman &lt;orkunkaraduman@gmail.com&gt;

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see &lt;http://www.gnu.org/licenses/&gt;.
