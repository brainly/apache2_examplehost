apache2_examplehost
========

This role serves as an example usage of apache2_base role. It provides a simple
setup where Apache serves PHP's phpinfo page.

Requirements
------------

The role was tested using Ansible 1.6 but it should be OK to use 1.4-1.5.

Role Variables
--------------

Role itself does not have any tweakable variables.

Dependencies
------------

This role depends on apache2_base, and beside that there are no other
dependencies. The role alone will not produce usable HTTP server.

Example Playbook
-------------------------

Applying the role is straightforward:
* make sure that both apache2_base and apache2_examplehost roles are present in
  your role directory.
* apache2_examplehost should have apache2_base as it's dependency. From
  meta.yml:

  ```
  ...
dependencies:
  - {role: apache2_base, apache2_base_php_enabled: True}
  ...
  ```

  apache2_base vars  may be specified in the meta.yml file or in group_vars/
  and/or host_vars/

* apply apache2_examplehost to your playbook:

  ```
  - hosts: www-servers
    roles:
      - apache2_examplehost
  ```

License
-------

Copyright 2014 Zadane.pl sp. z o.o.

Copyright 2014 Pawel Rozlach

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this role except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.


Author Information
------------------

This role has been created by Pawel Rozlach. It's partially based on the work
and expirience gathered at Zadane.pl sp. z o.o.
