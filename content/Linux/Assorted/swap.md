---
title: Swap Memory
author: csmertx
date: January 30, 2023
weight: -20
---

## A swapfile (1G)

- ```sudo dd if=/dev/zero of=/swap1G bs=1024 count=1048576```

- ```sudo chown root:root /swap1G```

- ```sudo chmod 0600 /swap1G```

- ```sudo mkswap /swap1G```

- ```sudo swapon /swap1G```

- ```sudov /etc/fstab```

    ```
    ++ /swap1G none swap sw 0 0
    ```

## Resources

- [Linux.com: All about Linux swap space](https://www.linux.com/news/all-about-linux-swap-space/)
