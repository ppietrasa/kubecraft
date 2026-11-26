$ docker exec -it clab-routing-basics-srl1 sr_cli -c "show interface brief"
+---------------------+---------------------------+---------------------------+---------------------------+---------------------------+---------------------------+
|        Port         |        Admin State        |        Oper State         |           Speed           |           Type            |        Description        |
+=====================+===========================+===========================+===========================+===========================+===========================+
| ethernet-1/1        | enable                    | up                        | 25G                       |                           |                           |
| ethernet-1/2        | enable                    | up                        | 25G                       |                           |                           |
| ethernet-1/3        | **disable**                   | down                      | 25G                       |                           |                           |
| ethernet-1/4        | disable                   | down                      | 25G                       |                           |                           |

Why route existence does not guarantee path availability?

Route is just an entry in the table. It is not guaranteed that the
infrastructure supporting the route is working properly. In this exercise the
NIC has been administratively disabled. In the field, bad quality links e.g. a
wave interference on the WiFi interface, congestions, etc.  impact path
availability.
