Ansible Playbook: awx-api-inventory
===================================

Example playbook that automates AWX REST API interactions to disable or remove a host from static inventory.

How does it works
------------------

- Discover inventory id
- Discover host id
- Disable host in static inventory (if declared by variable)
- Remove host in static inventory (if declared by variable)

For inventory id, by default it uses internal variables from Ansible Tower and AWX (e.g. awx_inventory_name).

Requirements
------------

Ansible Tower/AWX access.

Playbook Variables
------------------

The **awx-api-inventory** playbook is configured over variables starting with `api_` as the name prefix.

List of variables:

| Variable                | Type        | Description                            |
|-------------------------|-------------|----------------------------------------|
| `api_awx_url`           | string (m)  | AWX/Tower URL                          |
| `api_awx_username`      | string (m)  | AWX/Tower user name                    |
| `api_awx_password`      | string (m)  | AWX/Tower user password                |
| `api_awx_inventory`     | string (m)  | AWX/Tower inventory name to be manage  |
| `api_inventory_disable` | boolean (o) | Disable the managed host in inventory  |
| `api_inventory_remove`  | boolean (o) | Remove the managed host from inventory |

(m) - mandatory  
(o) - optional  

Explained list of variables:

- `api_awx_url`: AWX/Tower URL

  type: string

  affected files: n/a

  example:

  ```yaml
  api_awx_url: "https://awx.example.com"
  ```

- `api_awx_username`: AWX/Tower user name

  type: string

  affected files: n/a

  example:

  ```yaml
  api_awx_username: admin
  ```

- `api_awx_password`: AWX/Tower user password

  type: string

  affected files: n/a

  example:

  ```yaml
  api_awx_password: mypassword
  ```

- `api_awx_inventory`: AWX/Tower inventory name to be managed, default value is dynamic

  type: string

  affected files: n/a

  example:

  ```yaml
  api_awx_inventory: Example Inventory
  ```

- `api_inventory_disable`: disable the managed node in inventory

  type: boolean

  affected files: n/a

  example:

  ```yaml
  api_inventory_disable: no
  ```

- `api_inventory_remove`: remove the managed node from inventory

  type: boolean

  affected files: n/a

  example:

  ```yaml
  api_inventory_remove: no
  ```

License
-------

MIT

Author Information
------------------

This playbook was created in 2019 by [Cláudio Domingos](https://linkedin.com/in/cadomingos)
