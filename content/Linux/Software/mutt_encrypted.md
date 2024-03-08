---
title: 💻 Mutt E-Mail Client
author: csmertx
date: February 4, 2023
weight: -20
---

<br />

## Using Mutt the safe way

> Encrypt plain text password file for added security

- ```gpg --gen-key```

- ```mkdir ~/.mutt```

- ```touch ~/.mutt/password```

- ```vim ~/.mutt/password```

    ```
    ++ mysecretpassword
    ```

- ```gpg -r myemail@email.com -e ~/.mutt/password```

    > Encrypts sensitive data

- edit out sensitive information

    > Check for original ```~/.mutt/password``` (without .gpg)

    - ```shred ~/.mutt/password```

        > If the original file remains--it's been a few years since I've used Mutt

- ```vim ~/.muttrc```

    ```
    ++ source "gpg -d ~/.mutt/password.gpg |" 
    ```

## Resources

- [The Mutt E-Mail Client](http://www.mutt.org/)

- [Xmodulo Linux FAQ: How to use Mutt email client with encrypted passwords](http://xmodulo.com/mutt-email-client-encrypted-passwords.html)
