---
title: 💻 Mutt E-Mail Client
author: Chris Schammert (csmertx -- Christopher Schammert )
published: 2023-02-04
weight: -20
---

<!-- The content of this website was written by Christopher Schammert aka Chris Schammert -->

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

<br />

<div style="text-align: center; font-size:12px; color:dimgray">
    Created: 12/29/2021 • Edited: 02/09/2025 • Author: Chris Schammert (csmertx) • 
    <a href="https://github.com/csmertx/csmertx.github.io/commits/main/content/Linux/Software/mutt_encrypted.md" 
       title="Github.com | csmertx \ csmertx.github.io \ commits \ main \ content \ Linux \ Software \ Mutt E-Mail Client">
       History 🕵️
    </a>
</div>