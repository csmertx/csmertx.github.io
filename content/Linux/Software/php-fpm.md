---
title: 💻 FastCGI (PHP-FPM)
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-04
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

## Enable Error Logging

- ```sudov /etc/php/php-fpm.d/www.conf```

- or ```sudov /usr/local/etc/php-fpm.d/www.conf```

    - Uncomment / Make Changes

        ```
        catch_workers_output = yes
        php_flag[display_errors] = on
        php_admin_value[error_log] = /var/log/fpm-php.www.log
        php_admin_flag[log_errors] = on
        php_admin_value[memory_limit] = 99M
        ```

- ```sudo touch /var/log/fpm-php.www.log```

- ```sudo chmod 777 /var/log/fpm-php.www.log```

## Check Error Log

- ```tail -f /var/log/fpm-php.www.log```
