---
title: 💻 Swap Memory
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-01-30
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

<br />

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
